---
title: "Validador de contrase&#241;a de nombre de usuario | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 42f03841-286b-42d8-ba58-18c75422bc8e
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# Validador de contrase&#241;a de nombre de usuario
Este ejemplo muestra cómo implementar un validador UserNamePassword personalizado.Esto es útil en casos donde ninguno de los modos de validación UserNamePassword integrados es apropiado para los requisitos de la aplicación; por ejemplo, cuando los pares nombre de usuario\/contraseña se almacenan en un almacén externo, como una base de datos.Este ejemplo muestra un servicio que tiene un validador personalizado que comprueba dos pares de nombre de usuario y contraseña determinados.El cliente usa un par de nombre de usuario y contraseña para autenticar en el servicio.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Extensibility\Security\UserNamePasswordValidator`  
  
> [!NOTE]
>  Dado que cualquiera puede construir una credencial de nombre de usuario que utilice los pares de nombre de usuario y contraseña que el validador personalizado acepta, el servicio es menos seguro que el comportamiento predeterminado proporcionado por el validador UserNamePassword estándar.El validador UserNamePassword estándar intenta asignar el par de nombre de usuario\/contraseña proporcionado a una cuenta de Windows y si esta asignación no es correcta, se produce un error en la autenticación.El validador UserNamePassword personalizado en este ejemplo NO SE DEBE utilizar en el código de producción, solo es para fines informativos.  
  
 En resumen, este ejemplo muestra cómo:  
  
-   Se puede autenticar el cliente con un token de nombre de usuario.  
  
-   El servidor valida las credenciales del cliente con un UserNamePasswordValidator personalizado y cómo propagar los errores personalizados desde la lógica de validación del nombre de usuario y la contraseña al cliente.  
  
-   El servidor se autentica utilizando el certificado X.509 del servidor.  
  
 El servicio expone un extremo único para comunicarse con el servicio, definido usando el archivo de configuración App.config.El extremo está compuesto por una dirección, un enlace y un contrato.El enlace se configura con un `wsHttpBinding` estándar que tiene como valor predeterminado usar la autenticación de WS\-Securityy nombre de usuario.El comportamiento del servicio especifica el modo `Custom` para validar los pares de nombre de usuario y contraseña del cliente con el tipo de la clase de validador.El comportamiento también especifica el certificado de servidor mediante el elemento `serviceCertificate`.El certificado de servidor tiene que contener el mismo valor para `SubjectName` como `findValue` en [\<serviceCertificate\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).  
  
```  
<system.serviceModel>  
  <services>  
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
      <!-- use host/baseAddresses to configure base address provided by host -->  
      <host>  
        <baseAddresses>  
          <add baseAddress ="http://localhost:8001/servicemodelsamples/service" />  
        </baseAddresses>  
      </host>  
      <!-- use base address specified above, provide one endpoint -->  
      <endpoint address="username"  
                binding="wsHttpBinding"  
                bindingConfiguration="Binding"   
                contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>  
  
  <bindings>  
    <wsHttpBinding>  
      <!-- username binding -->  
      <binding name="Binding">  
        <security mode="Message">  
          <message clientCredentialType="UserName" />  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="CalculatorServiceBehavior">  
        <serviceDebug includeExceptionDetailInFaults ="true"/>  
        <serviceCredentials>  
          <!--   
          The serviceCredentials behavior allows one to   
          specify a custom validator for username/password  
          combinations.  
          -->  
          <userNameAuthentication userNamePasswordValidationMode="Custom"  
                                  customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService+MyCustomUserNameValidator, service" />  
          <!--   
          The serviceCredentials behavior allows one to define a service certificate. A service certificate is used by a client to authenticate the service and provide message protection. You must specify a server certificate when passing username/passwords to encrypt the information as it is sent on the wire. Otherwise the username and password information would be sent as clear text. This configuration references the "localhost" certificate installed during the setup instructions.  
          -->  
          <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
        </serviceCredentials>  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
  
</system.serviceModel>  
  
```  
  
 La configuración de extremo de cliente está compuesta de un nombre de configuración, una dirección absoluta para el extremo de servicio, el enlace y el contrato.El enlace del cliente se configura con el modo adecuado y el `clientCredentialType` del mensaje.  
  
```  
<system.serviceModel>  
  
    <client>  
      <!-- Username based endpoint -->  
      <endpoint name="Username"  
address="http://localhost:8001/servicemodelsamples/service/username"   
                binding="wsHttpBinding"   
                bindingConfiguration="Binding"   
                behaviorConfiguration="ClientCertificateBehavior"  
                contract="Microsoft.ServiceModel.Samples.ICalculator">  
      </endpoint>  
    </client>  
  
    <bindings>  
      <wsHttpBinding>  
        <!-- Username binding -->  
        <binding name="Binding">  
          <security mode="Message">  
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="ClientCertificateBehavior">  
          <clientCredentials>  
            <serviceCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certification authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust" />  
            </serviceCertificate>  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
  
```  
  
 La implementación del cliente pide al usuario que introduzca un nombre de usuario y una contraseña.  
  
```  
// Get the username and password  
Console.WriteLine("Username authentication required.");  
Console.WriteLine("Provide a username.");  
Console.WriteLine("   Enter username: (test1)");  
string username = Console.ReadLine();  
Console.WriteLine("   Enter password:");  
string password = "";  
ConsoleKeyInfo info = Console.ReadKey(true);  
while (info.Key != ConsoleKey.Enter)  
{  
    if (info.Key != ConsoleKey.Backspace)  
    {  
        if (info.KeyChar != '\0')  
        {  
            password += info.KeyChar;  
        }  
        info = Console.ReadKey(true);  
    }  
    else if (info.Key == ConsoleKey.Backspace)  
    {  
        if (password != "")  
        {  
            password = password.Substring(0, password.Length - 1);  
        }  
        info = Console.ReadKey(true);  
    }  
}  
for (int i = 0; i < password.Length; i++)  
{  
    Console.Write("*");  
}  
Console.WriteLine();  
// Create a proxy with Certificate endpoint configuration  
CalculatorProxy proxy = new CalculatorProxy("Username")  
try  
{  
  proxy.ClientCredentials.Username.Username = username;  
  proxy.ClientCredentials.Username.Password = password;  
    // Call the Add service operation.  
    double value1 = 100.00D;  
    double value2 = 15.99D;  
    double result = proxy.Add(value1, value2);  
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  }  
  catch (Exception e)  
  {  
      Console.WriteLine("Call failed:");  
      while (e != null)  
      {  
          Console.WriteLine("\t{0}", e.Message);  
          e = e.InnerException;  
      }  
      proxy.Abort();  
  }  
}  
  
```  
  
 Este ejemplo utiliza un UserNamePasswordValidator personalizado para validar pares de nombre de usuario y contraseña.El ejemplo implementa `CustomUserNamePasswordValidator`, derivado de <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.Consulte la documentación existente sobre <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> para obtener más información.Este ejemplo de validador personalizado determinado implementa el método `Validate` para aceptar dos pares de nombre de usuario y contraseña determinados tal y como se muestran en el código siguiente.  
  
```  
public class CustomUserNameValidator : UserNamePasswordValidator  
{  
 // This method validates users. It allows in two users,   
 // test1 and test2 with passwords 1tset and 2tset respectively.  
 // This code is for illustration purposes only and   
 // MUST NOT be used in a production environment because it   
 // is NOT secure.  
 public override void Validate(string userName, string password)  
 {  
  if (null == userName || null == password)  
  {  
   throw new ArgumentNullException();  
  }  
  
  if (!(userName == "test1" && password == "1tset") && !(userName == "test2" && password == "2tset"))  
  {  
   throw new FaultException("Unknown Username or Incorrect Password");  
   }  
  }  
 }  
```  
  
 Una vez que se implementa el validador en el código de servicio, se debe informar al host de servicio sobre la instancia del validador que se va a usar.Esto se hace mediante el código siguiente.  
  
```  
serviceHost.Credentials.UserNameAuthentication.UserNamePasswordValidationMode = UserNamePasswordValidationMode.Custom;  
serviceHost.Credentials. UserNameAuthentication.CustomUserNamePasswordValidator = new CustomUserNamePasswordValidator();  
```  
  
 O puede hacer lo mismo en la configuración tal y como se explica a continuación.  
  
```  
<behaviors>  
 <serviceBehaviors>  
  <behavior name="CalculatorServiceBehavior">  
  ...  
   <serviceCredentials>  
    <!--   
    The serviceCredentials behavior allows one to specify authentication constraints on username / password combinations.  
    -->  
    <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService+CustomUserNameValidator, service" />  
   ...  
  </behavior>  
 </serviceBehaviors>  
</behaviors>  
  
```  
  
 Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.El cliente debería llamar correctamente a todos los métodos.Presione ENTRAR en la ventana de cliente para cerrar el cliente.  
  
## Instalar el archivo por lotes  
 El archivo por lotes Setup.bat incluido con este ejemplo le permite configurar el servidor con los certificados pertinentes para ejecutar una aplicación autohospedada que exija la seguridad basada en el certificado del servidor.Este archivo por lotes debe modificarse para que funcione en los equipos o en un caso no autohospedado.  
  
 A continuación, se proporciona información general breve de las diferentes secciones de los archivos por lotes para que se puedan modificar a fin de ejecutarse con la configuración adecuada.  
  
-   Crear el certificado de servidor:  
  
     Las líneas siguientes del archivo por lotes Setup.bat crean el certificado de servidor que se va a usar.La variable %SERVER\_NAME% especifica el nombre del servidor.Cambie esta variable para especificar el nombre del servidor.El valor predeterminado es el host local.  
  
    ```  
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
  
    ```  
  
-   Instalar el certificado del servidor en el almacén de certificados de confianza del cliente:  
  
     Las líneas siguientes del archivo por lotes Setup.bat copian el certificado de servidor en el almacén de usuarios de confianza del cliente.Este paso es necesario porque el sistema cliente no confía implícitamente en los certificados generados por Makecert.exe.Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente, por ejemplo, un certificado emitido por Microsoft, no es necesario el paso de rellenar el almacén del certificado de cliente con el certificado de servidor.  
  
    ```  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
#### Para configurar y compilar el ejemplo  
  
1.  Para compilar la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2.  Para ejecutar el ejemplo en una configuración de equipos única o cruzada, utilice las instrucciones siguientes.  
  
#### Para ejecutar el ejemplo en el mismo equipo  
  
1.  Ejecute el archivo Setup.bat de la carpeta de instalación del ejemplo dentro de un símbolo del sistema de [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].De esta forma, se instalan todos los certificados necesarios para ejecutar el ejemplo.  
  
    > [!NOTE]
    >  El archivo por lotes Setup.bat está diseñado para ejecutarse desde un símbolo del sistema de [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].La variable de entorno PATH que se establece en el símbolo del sistema de [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] señala al directorio que contiene los archivos ejecutables que requiere el script Setup.bat.  
  
2.  Inicie Service.exe desde \\service\\bin.  
  
3.  Inicie Client.exe desde \\client\\bin.La actividad del cliente se muestra en la aplicación de consola del cliente.  
  
4.  Si el cliente y el servicio no se pueden comunicar, vea [Troubleshooting Tips](http://msdn.microsoft.com/es-es/8787c877-5e96-42da-8214-fa737a38f10b).  
  
#### Para ejecutar el ejemplo en varios equipos  
  
1.  Cree un directorio en el equipo del servicio para los binarios del servicio.  
  
2.  Copie los archivos del programa de servicio en el directorio de servicio situado en el equipo del servicio.Copie también los archivos Setup.bat y Cleanup.bat en el equipo del servicio.  
  
3.  Necesita un certificado de servidor con el nombre del sujeto que contiene el nombre de dominio completo del equipo.El archivo de configuración para el servidor debe estar actualizado para reflejar este nuevo nombre del certificado.  
  
4.  Copie el certificado de servidor en el almacén de CurrentUser\-TrustedPeople del cliente.Solo necesita hacerlo si el certificado del servidor no está emitido por el emisor de confianza.  
  
5.  En el archivo App.config situado en el equipo de servicio, cambie el valor de la dirección base para especificar un nombre de equipo completo en lugar del host local.  
  
6.  En el equipo de servicio, inicie Service.exe desde una ventana de símbolo del sistema.  
  
7.  Copie los archivos de programa del cliente de la carpeta \\client\\bin\\, bajo la carpeta específica del lenguaje, al equipo del cliente.  
  
8.  En el archivo Client.exe.config del equipo cliente, cambie el valor de la dirección del extremo para que coincida con la nueva dirección de su servicio.  
  
9. En el equipo cliente, inicie Client.exe desde la ventana de símbolo del sistema.  
  
10. Si el cliente y el servicio no se pueden comunicar, vea [Troubleshooting Tips](http://msdn.microsoft.com/es-es/8787c877-5e96-42da-8214-fa737a38f10b).  
  
#### Para limpiar después del ejemplo  
  
1.  Ejecute Cleanup.bat en la carpeta de ejemplos cuando haya terminado de ejecutar el ejemplo.Así se elimina el certificado del servidor del almacén de certificados.  
  
## Vea también
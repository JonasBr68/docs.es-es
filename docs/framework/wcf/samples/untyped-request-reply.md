---
title: "Solicitud/respuesta sin tipo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0bf0f9d9-7caf-4d3d-8c9e-2d468cca16a5
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Solicitud/respuesta sin tipo
Este ejemplo muestra cómo definir contratos de operación que utilizan la clase de mensaje.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 Este ejemplo se basa en el [Introducción:](../../../../docs/framework/wcf/samples/getting-started-sample.md).El contrato de servicios define una operación que toma un tipo de mensaje como argumento y devuelve un mensaje.La operación recoge todos los datos necesarios para calcular la suma a partir del cuerpo del mensaje y, a continuación, la envía como cuerpo en el mensaje de retorno.  
  
```  
  
[OperationContract(Action = CalculatorService.RequestAction, ReplyAction = CalculatorService.ReplyAction)]  
Message ComputeSum(Message request);  
  
```  
  
 En el servicio, la operación recupera la matriz de enteros pasada en el mensaje de entrada y, a continuación, calcula la suma.Para enviar un mensaje de respuesta, el ejemplo crea un nuevo mensaje con la versión de mensaje y la acción adecuadas, y agrega la suma calculada como su cuerpo.En el siguiente ejemplo de código se muestra este caso.  
  
```  
  
public Message ComputeSum(Message request)  
{  
    //The body of the message contains a list of numbers which will be   
    //read as a int[] using GetBody<T>  
    int result = 0;  
  
    int[] inputs = request.GetBody<int[]>();  
    foreach (int i in inputs)  
    {  
        result += i;  
    }  
  
    Message response = Message.CreateMessage(request.Version,   
                                      ReplyAction, result);  
    return response;  
}  
  
```  
  
 El cliente utiliza código generado por [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para crear un proxy al servicio remoto.Para enviar un mensaje de solicitud, el cliente debe tener la versión del mensaje, que depende del canal subyacente.Así, crea un nuevo <xref:System.ServiceModel.OperationContextScope> en el ámbito del canal de proxy que creó, que genera un <xref:System.ServiceModel.OperationContext> con la versión de mensaje correcta en su propiedad `OutgoingMessageHeaders.MessageVersion`.El cliente pasa una matriz de entrada como el cuerpo al mensaje de solicitud y, a continuación, invoca `ComputeSum` en el proxy.El cliente recupera a continuación la suma de las entradas por las que pasó teniendo acceso al método `GetBody<T>` en el mensaje de respuesta.En el siguiente ejemplo de código se muestra este caso.  
  
```  
  
using (new OperationContextScope(client.InnerChannel))  
{  
    // Call the Sum service operation.  
    int[] values = { 1, 2, 3, 4, 5 };  
    Message request = Message.CreateMessage(  
        OperationContext.Current.OutgoingMessageHeaders.MessageVersion,   
        RequestAction, values);  
    Message reply = client.ComputeSum(request);  
    int response = reply.GetBody<int>();  
  
    Console.WriteLine("Sum of numbers passed (1,2,3,4,5) = {0}",   
                                                       response);  
}  
  
```  
  
 Este ejemplo es un ejemplo hospedado en web y, por tanto, solo se debe ejecutar la aplicación ejecutable del cliente.Lo siguiente es el resultado del ejemplo en el cliente.  
  
```  
  
Prompt>Client.exe  
Sum of numbers passed (1,2,3,4,5) = 15  
  
Press <ENTER> to terminate client.  
  
```  
  
 Este ejemplo es un ejemplo hospedado en web. Por tanto, compruebe el vínculo proporcionado en el paso 3 para ver cómo compilar y ejecutar el ejemplo.  
  
### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de realizar los [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar el código C\# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Para ejecutar el ejemplo en una configuración con un único equipo o con varios, siga las instrucciones de [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Contract\Message\Untyped`  
  
## Vea también
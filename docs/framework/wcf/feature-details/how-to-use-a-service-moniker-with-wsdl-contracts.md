---
title: "Cómo: Utilizar un moniker de servicio con contratos WSDL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a88d9650-bb50-4f48-8c85-12f5ce98a83a
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7c36ac73ced510c1ba3b7e16c71f764c46d6c8f9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-service-moniker-with-wsdl-contracts"></a>Cómo: Utilizar un moniker de servicio con contratos WSDL
Hay situaciones en las que usted querrá tener un cliente de Interoperabilidad COM completamente autónomo. Puede que el servicio que quiere llamar no exponga un extremo MEX y puede que la DLL cliente de WCF no se registre para la interoperabilidad COM. En estos casos, puede crear un archivo WSDL que describe el servicio y lo pasa en el moniker del servicio WCF. Este tema describe cómo llamar al ejemplo de WCF Introducción utilizando un moniker WSDL de WCF.  
  
### <a name="using-the-wsdl-service-moniker"></a>Utilizar el moniker de servicio WSDL  
  
1.  Abra y compile la solución de ejemplo GettingStarted.  
  
2.  Abra Internet Explorer y vaya a http://localhost/ServiceModelSamples/Service.svc para asegurarse de que el servicio está funcionando.  
  
3.  En el archivo Service.cs, agregue el atributo siguiente en la clase CalculatorService:  
  
     [!code-csharp[S_WSDL_Client#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wsdl_client/cs/service.cs#0)]  
  
4.  Agregue un espacio de nombres de enlace al servicio App.config:  
  
  
  
5.  Cree un archivo WSDL para que lo lea la aplicación. Dado que los espacios de nombres se agregaron en los pasos 3 y 4, puede utilizar IE para consultar la descripción WSDL completa del servicio yendo a http://localhost/ServiceModelSamples/Service.svc?wsdl. Puede guardar a continuación el archivo desde Internet Explorer como serviceWSDL.xml. Si no especifica los espacios de nombres en los pasos 3 y 4, el documento WSDL devuelto de la consulta a la dirección URL anterior no será el WSDL completo. El documento WSDL devuelto incluirá varias instrucciones de importación que importan otros documentos WSDL. Tendrá que pasar por cada instrucción de importación y crear el documento WSDL completo, combinando el WSDL devuelto desde el servicio con el WSDL importado.  
  
6.  Abra Visual Basic 6.0 y cree un nuevo archivo .exe estándar. Agregue un botón al formulario y haga doble clic en él para agregar el código siguiente al controlador de clic:  
  
    ```  
    ' Open the WSDL contract file and read it all into the wsdlContract string.  
    Const ForReading = 1  
    Set objFSO = CreateObject("Scripting.FileSystemObject")  
    Set objFile = objFSO.OpenTextFile("c:\serviceWsdl.xml", ForReading)  
    wsdlContract = objFile.ReadAll  
    objFile.Close  
  
    ' Create a string for the service moniker including the content of the WSDL contract file.  
    wsdlMonikerString = "service4:address='http://localhost/ServiceModelSamples/service.svc'"  
    wsdlMonikerString = wsdlMonikerString + ", wsdl='" & wsdlContract & "'"  
    wsdlMonikerString = wsdlMonikerString + ", binding=WSHttpBinding_ICalculator, bindingNamespace='http://Microsoft.ServiceModel.Samples'"  
    wsdlMonikerString = wsdlMonikerString + ", contract=ICalculator, contractNamespace='http://Microsoft.ServiceModel.Samples'"  
  
    ' Create the service moniker object.  
    Set wsdlServiceMoniker = GetObject(wsdlMonikerString)  
  
    ' Call the service operations using the moniker object.  
    MsgBox "WSDL service moniker: 145 - 76.54 = " & wsdlServiceMoniker.Subtract(145, 76.54)  
    ```  
  
    > [!NOTE]
    >  Si el moniker es incorrecto o si el servicio no está disponible la llamada a `GetObject` devolverá un error que dirá "Sintaxis no válida."  Si recibe este error, asegúrese de que el moniker que está utilizando es correcto y el servicio está disponible.  
  
7.  Ejecutar aplicación de Visual Basic Se mostrará un cuadro de mensaje con los resultados de llamar a Subtract (145, 76.54).  
  
## <a name="see-also"></a>Vea también  
 [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [Integración en la información general de las aplicaciones COM+](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications-overview.md)

---
title: "Cómo: Conectar varios eventos con un único controlador de eventos en formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- vb
helpviewer_keywords:
- events [Windows Forms], connecting multiple to single event handler
- event handlers [Windows Forms], connecting events to
- menus [Windows Forms], event-handling methods for multiple menu items
- Windows Forms controls, events
- menu items [Windows Forms], multicasting event-handling methods
ms.assetid: 5a20749a-41b5-4acc-8eb1-9e5040b0a2c4
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bfd955b4153c7a2bc54d8b52ff1801541c3a7559
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a>Cómo: Conectar varios eventos con un único controlador de eventos en formularios Windows Forms
En el diseño de aplicaciones, le resultará necesario usar un único controlador de eventos para varios eventos o tener varios eventos, realice el mismo procedimiento. Por ejemplo, a menudo resulta ahorrar mucho tiempo si un comando de menú producen el mismo evento como un botón en el formulario si expone la misma funcionalidad. Puede hacerlo mediante la vista de eventos de la ventana Propiedades en C# o mediante el `Handles` palabra clave y el **nombre de la clase** y **nombre del método** cuadros de lista desplegable en el Editor de código de Visual Basic.  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a>Para conectar varios eventos con un único controlador de eventos en Visual Basic  
  
1.  Haga clic en el formulario y elija **ver código**.  
  
2.  Desde el **nombre de la clase** cuadro de lista desplegable, seleccione uno de los controles que desea agregar el controlador de eventos.  
  
3.  Desde el **nombre del método** cuadro de lista desplegable, seleccione uno de los eventos que desea agregar un controlador de eventos.  
  
4.  El Editor de código se inserta el controlador de eventos apropiado y se coloca el punto de inserción dentro del método. En el ejemplo siguiente, es el <xref:System.Windows.Forms.Control.Click> eventos para el <xref:System.Windows.Forms.Button> control.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5.  Agregue los otros eventos que desea que administran el `Handles` cláusula.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6.  Agregue el código correspondiente al controlador de eventos.  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a>Para conectar varios eventos con un único controlador de eventos en C#  
  
1.  Seleccione el control al que desea conectarse a un controlador de eventos.  
  
2.  En la ventana Propiedades, haga clic en el **eventos** botón (![botón eventos](../../../docs/framework/winforms/media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).  
  
3.  Haga clic en el nombre del evento que desea controlar.  
  
4.  En la sección de valor junto al nombre del evento, haga clic en el botón de lista desplegable para mostrar una lista de controladores de eventos existentes que coincidan con la firma del método del evento que desea controlar.  
  
5.  Seleccione el controlador de eventos apropiado en la lista.  
  
     Se agregará código al formulario para enlazar el evento al controlador de eventos existente.  
  
## <a name="see-also"></a>Vea también  
 [Crear controladores de eventos en Windows Forms](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [Información general sobre controladores de eventos](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)

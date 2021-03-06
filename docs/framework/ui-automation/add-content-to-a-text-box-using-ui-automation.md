---
title: Agregar contenido a un cuadro de texto utilizando la UI Automation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adding content to text boxes
- text boxes, adding content
- UI Automation, adding content to text boxes
ms.assetid: 8bdd1a73-1ecb-4a05-a891-a7827ebb767f
caps.latest.revision: "13"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: edc11040a782151af83cb9318ab424426c712e0a
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="add-content-to-a-text-box-using-ui-automation"></a>Agregar contenido a un cuadro de texto utilizando la UI Automation
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Este tema contiene código de ejemplo que muestra cómo utilizar [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] para insertar texto en un cuadro de texto multilínea. Se proporciona un método alternativo para los controles de varias líneas y de texto enriquecido donde [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] no es aplicable. Para realizar una comparación, el ejemplo también muestra cómo utilizar métodos de Win32 para lograr los mismos resultados.  
  
## <a name="example"></a>Ejemplo  
 Los siguientes pasos de ejemplo a través de una secuencia de controles de texto en una aplicación de destino. Cada control de texto se prueba para ver si hay un <xref:System.Windows.Automation.ValuePattern> objeto puede obtenerse mediante la <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> método. Si el control de texto admite <xref:System.Windows.Automation.ValuePattern>, el <xref:System.Windows.Automation.ValuePattern.SetValue%2A> método se utiliza para insertar una cadena definida por el usuario en el control de texto. En caso contrario, el <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> se utiliza el método.  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## <a name="see-also"></a>Vea también  
 [Ejemplo de texto de inserción de TextPattern](http://msdn.microsoft.com/library/67353f93-7ee2-42f2-ab76-5c078cf6ca16)

---
title: "Cómo: recuperar una colección de elementos (LINQ to XML) (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2269f9de-8fb9-4666-b8a1-a4e754fa6a81
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a3d8cc558191b1ad672660e0d9ada4c4653cd1a7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-retrieve-a-collection-of-elements-linq-to-xml-visual-basic"></a>Cómo: recuperar una colección de elementos (LINQ to XML) (Visual Basic)
En este tema se demuestra el método <xref:System.Xml.Linq.XContainer.Elements%2A>. Este método recupera una colección de elementos secundarios de un elemento.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo recorre en iteración los elementos secundarios del elemento `purchaseOrder`.  
  
 En este ejemplo se usa el siguiente documento XML: [Archivo XML de ejemplo: Pedido de compra común (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).  
  
```vb  
Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
Dim childElements As IEnumerable(Of XElement)  
childElements = _  
    From el In po.Elements() _  
    Select el  
For Each el As XElement In childElements  
    Console.WriteLine("Name: " & el.Name.ToString())  
Next  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
Name: Address  
Name: Address  
Name: DeliveryNotes  
Name: Items  
```  
  
## <a name="see-also"></a>Vea también  
 [Ejes de LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)

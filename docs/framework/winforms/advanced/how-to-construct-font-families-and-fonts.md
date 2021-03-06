---
title: "Cómo: Construir fuentes y familias de fuentes"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- font families [Windows Forms], constructing
- fonts [Windows Forms], constructing
ms.assetid: d3a4a223-9492-4b54-9afd-db1c31c3cefd
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e152c525550554082d7d6c38a972ccc150adabb9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-construct-font-families-and-fonts"></a>Cómo: Construir fuentes y familias de fuentes
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]agrupa las fuentes con el mismo tipo de letra pero distintos estilos en familias de fuentes. Por ejemplo, la familia de fuentes Arial contiene las siguientes fuentes:  
  
-   Arial normal  
  
-   Arial negrita  
  
-   Arial cursiva  
  
-   Arial negrita cursiva  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]utiliza cuatro estilos para formar familias: normal, negrita, cursiva y negrita cursiva. Adjetivos como *restringir* y *redondea* no se consideran estilos; en su lugar forman parte del nombre de familia. Por ejemplo, Arial Narrow es una familia de fuentes con los miembros siguientes:  
  
-   Arial Narrow Normal  
  
-   Arial Narrow negrita  
  
-   Arial Narrow Cursiva  
  
-   Arial Narrow negrita cursiva  
  
 Antes de poder dibujar texto con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], deberá construir un <xref:System.Drawing.FontFamily> objeto y un <xref:System.Drawing.Font> objeto. El <xref:System.Drawing.FontFamily> objeto especifica el tipo de letra (por ejemplo, Arial) y el <xref:System.Drawing.Font> objeto especifica el tamaño, estilo y las unidades.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un estilo normal fuente Arial con un tamaño de 16 píxeles. En el código siguiente, el primer argumento pasado a la <xref:System.Drawing.Font.%23ctor%2A> constructor es el <xref:System.Drawing.FontFamily> objeto. El segundo argumento especifica el tamaño de la fuente medido en unidades identificadas por el cuarto argumento. El tercer argumento identifica el estilo.  
  
 <xref:System.Drawing.GraphicsUnit.Pixel>es un miembro de la <xref:System.Drawing.GraphicsUnit> enumeración, y <xref:System.Drawing.FontStyle.Regular> es un miembro de la <xref:System.Drawing.FontStyle> enumeración.  
  
 [!code-csharp[System.Drawing.FontsAndText#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.FontsAndText#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vea también  
 [Utilizar fuentes y texto](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)

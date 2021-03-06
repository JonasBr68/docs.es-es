---
title: "Tipo de &#39; &lt;typename&gt;&#39; no está definido"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 68eb37f43600c51dc9117c3785a12e3c8ede1965
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="type-39lttypenamegt39-is-not-defined"></a>Tipo de &#39; &lt;typename&gt;&#39; no está definido
La instrucción ha hecho referencia a un tipo que no se ha definido. Puede definir un tipo en una instrucción de declaración como `Enum`, `Structure`, `Class`, o `Interface`.  
  
 **Id. de error:** BC30002  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Asegúrese de que la definición de tipo y su referencia utilizan la misma ortografía.  
  
-   Asegúrese de que la definición de tipo es accesible para la referencia. Por ejemplo, si el tipo está en otro módulo y se ha declarado `Private`, mueva la definición de tipo al que hace referencia a módulo o declárelo `Public`.  
  
-   Asegúrese de que el espacio de nombres del tipo no se vuelve a definir dentro de su proyecto. Si es así, utilice el `Global` palabra clave para calificar totalmente el nombre de tipo. Por ejemplo, si un proyecto que define un espacio de nombres denominado `System`, el <xref:System.Object?displayProperty=nameWithType> tipo no son accesibles a menos que esté completo con el `Global` palabra clave: `Global.System.Object`.  
  
-   Si el tipo está definido, pero no se registra la biblioteca de objetos o la biblioteca de tipos en el que se define en [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], haga clic en **Agregar referencia** en el **proyecto** menú y, a continuación, seleccione el objeto apropiado biblioteca o biblioteca de tipos.  
  
-   Asegúrese de que el tipo está en un ensamblado que forma parte del perfil de .NET Framework de destino. Para obtener más información, consulte [Solucionar problemas de versión de .NET Framework de destino](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).  
  
## <a name="see-also"></a>Vea también  
 [Espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [Enum (instrucción)](../../../visual-basic/language-reference/statements/enum-statement.md)  
 [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Administrar referencias en un proyecto](/visualstudio/ide/managing-references-in-a-project)

---
title: Nothing y cadenas en Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6ce9f81f23f50e38f6b1ad5e638e8c6ac026e992
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="nothing-and-strings-in-visual-basic"></a>Nothing y cadenas en Visual Basic
El [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] en tiempo de ejecución y el [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] evaluar `Nothing` forma diferente cuando se trata de cadenas.  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a>En tiempo de ejecución de Visual Basic y .NET Framework  
 Considere el ejemplo siguiente:  
  
 [!code-vb[VbVbalrStrings#47](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/nothing-and-strings_1.vb)]  
  
 El [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] normalmente se evalúa como el tiempo de ejecución `Nothing` como una cadena vacía (""). El [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] no es así, sin embargo y producirá una excepción cuando se realiza un intento para realizar una operación de cadena en `Nothing`.  
  
## <a name="see-also"></a>Vea también  
 [Introducción a las cadenas en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)

---
title: "Cómo: Obtener un valor de una propiedad (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6cde5408ea09398a79a3da01ae9b2d0202c58eaf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a>Cómo: Obtener un valor de una propiedad (Visual Basic)
Recupera el valor de una propiedad incluyendo el nombre de propiedad en una expresión.  
  
 La propiedad `Get` procedimiento recupera el valor, pero no llamar explícitamente a él por su nombre. Use la propiedad tal como utilizaría una variable. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]realiza las llamadas a procedimientos de la propiedad.  
  
### <a name="to-retrieve-a-value-from-a-property"></a>Para recuperar un valor de una propiedad  
  
1.  Utilice el nombre de propiedad en una expresión de la misma manera que usaría un nombre de variable. Puede usar una propiedad en cualquier lugar puede usar una variable o una constante.  
  
     O bien  
  
     Utilice el nombre de la propiedad siguiendo la igual (`=`) iniciar sesión en una instrucción de asignación.  
  
     En el ejemplo siguiente se lee el valor de la [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] `Now` propiedad, se llama implícitamente a su `Get` procedimiento.  
  
     [!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-get-a-value-from-a-property_1.vb)]  
  
2.  Si la propiedad toma argumentos, siga el nombre de propiedad entre paréntesis para delimitar la lista de argumentos. Si no hay ningún argumento, opcionalmente, puede omitir los paréntesis.  
  
3.  Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas. Asegúrese de que proporcionar los argumentos en el mismo orden que la propiedad define los parámetros correspondientes.  
  
 El valor de la propiedad participa en la expresión al igual que una variable o constante, o se almacena en la variable o propiedad en el lado izquierdo de la instrucción de asignación.  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)  
 [Procedimientos de propiedades](./property-procedures.md)  
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)  
 [Property (instrucción)](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [Diferencias entre propiedades y Variables en Visual Basic](./differences-between-properties-and-variables.md)  
 [Crear una propiedad](./how-to-create-a-property.md)  
 [Declarar una propiedad con niveles de acceso mixtos](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [Llamar a un procedimiento de propiedad](./how-to-call-a-property-procedure.md)  
 [Cómo: declarar y llamar a una propiedad predeterminada en Visual Basic](./how-to-declare-and-call-a-default-property.md)  
 [Establecer un valor en una propiedad](./how-to-put-a-value-in-a-property.md)

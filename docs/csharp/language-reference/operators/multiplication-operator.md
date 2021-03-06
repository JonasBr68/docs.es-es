---
title: '* Operador (Referencia de C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 64c32def0935f4347f9aaccc2865b9cd33dd8a70
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a>Operador * (Referencia de C#)
El operador de multiplicación (`*`), que calcula el producto de sus operandos.  Además, el operador de desreferencia, que permite leer y escribir en un puntero.  
  
## <a name="remarks"></a>Comentarios  
 Todos los tipos numéricos tienen operadores de multiplicación predefinidos.  
  
 El operador `*` también se usa para declarar tipos de puntero y desreferenciar punteros. Este operador solo puede usarse en contextos no seguros, que son en los que se usa la palabra clave [unsafe](../../../csharp/language-reference/keywords/unsafe.md) y que requieren la opción de compilador [/ unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).  El operador de desreferencia también se conoce como el operador de direccionamiento indirecto.  
  
 Los tipos definidos por el usuario pueden sobrecargar el operador binario `*` (consulte [operator](../../../csharp/language-reference/keywords/operator.md)). Cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si lo hay, también se sobrecarga de modo implícito.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#50](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#51](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_2.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)

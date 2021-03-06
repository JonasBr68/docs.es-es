---
title: Operator Statement
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.operator
helpviewer_keywords:
- operators [Visual Basic]
- procedures [Visual Basic], operator
- Narrowing keyword [Visual Basic], conversion operators
- Visual Basic code, operators
- Widening keyword [Visual Basic], conversion operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
- Operator statement [Visual Basic]
- CType function [Visual Basic], Operator statement
ms.assetid: b12ec4af-1ad7-4a17-865b-c5ee96320ae5
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1b6be45fd0a606f43c14d57f3f8ae0955f256ba6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="operator-statement"></a>Operator Statement
Declara el símbolo del operador, operandos y el código que definen un procedimiento de operador en una clase o estructura.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]   
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]  
    [ statements ]  
    [ statements ]  
    Return returnvalue  
    [ statements ]  
End Operator  
```  
  
## <a name="parts"></a>Elementos  
 `attrlist`  
 Opcional. Vea [lista de los atributos](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `Public`  
 Obligatorio. Indica que este procedimiento de operador tiene [público](../../../visual-basic/language-reference/modifiers/public.md) acceso.  
  
 `Overloads`  
 Opcional. Vea [sobrecargas](../../../visual-basic/language-reference/modifiers/overloads.md).  
  
 `Shared`  
 Obligatorio. Indica que este procedimiento de operador es un [Shared](../../../visual-basic/language-reference/modifiers/shared.md) procedimiento.  
  
 `Shadows`  
 Opcional. Vea [sombras](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
 `Widening`  
 Necesario para un operador de conversión a menos que especifique `Narrowing`. Indica que este procedimiento de operador define una [Widening](../../../visual-basic/language-reference/modifiers/widening.md) conversión. Vea "Ampliación y conversiones de restricción" en esta página de ayuda.  
  
 `Narrowing`  
 Necesario para un operador de conversión a menos que especifique `Widening`. Indica que este procedimiento de operador define una [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) conversión. Vea "Ampliación y conversiones de restricción" en esta página de ayuda.  
  
 `operatorsymbol`  
 Obligatorio. El símbolo o identificador del operador que define este procedimiento de operador.  
  
 `operand1`  
 Obligatorio. El nombre y el tipo de operando único de un operador unario (incluido un operador de conversión) o el operando izquierdo de un operador binario.  
  
 `operand2`  
 Se requiere para los operadores binarios. El nombre y tipo del operando derecho de un operador binario.  
  
 `operand1`y `operand2` tiene la sintaxis y las partes siguientes:  
  
 `[ ByVal ] operandname [ As operandtype ]`  
  
|Parte|Descripción|  
|----------|-----------------|  
|`ByVal`|Opcional, pero el mecanismo para pasar argumentos debe ser [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).|  
|`operandname`|Obligatorio. Nombre de la variable que representa este operando. Vea [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`operandtype`|Opcional, a menos que `Option Strict` es `On`. Tipo de datos de este operando.|  
  
 `type`  
 Opcional, a menos que `Option Strict` es `On`. Devuelve el tipo de datos del valor el procedimiento de operador.  
  
 `statements`  
 Opcional. Bloque de instrucciones que se ejecuta el procedimiento de operador.  
  
 `returnvalue`  
 Obligatorio. El valor que el procedimiento de operador devuelve al código de llamada.  
  
 `End` `Operator`  
 Requerido. Termina la definición de este procedimiento de operador.  
  
## <a name="remarks"></a>Comentarios  
 Puede usar `Operator` sólo en una clase o estructura. Esto significa que la *contexto de la declaración* para un operador no puede ser un archivo de código fuente, espacio de nombres, módulo, interfaz, procedimiento o bloque. Para obtener más información, vea [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).  
  
 Todos los operadores deben ser `Public Shared`. No se puede especificar `ByRef`, `Optional`, o `ParamArray` para alguno de los operandos.  
  
 No puede usar el símbolo del operador o el identificador para contener un valor devuelto. Debe utilizar el `Return` instrucción y deben especificar un valor. Cualquier número de `Return` instrucciones pueden aparecer en cualquier lugar en el procedimiento.  
  
 La definición de un operador de esta manera se denomina *sobrecarga de operadores*, utiliza o no el `Overloads` palabra clave. En la tabla siguiente se enumeran los operadores que se pueden definir.  
  
|Tipo|Operadores|  
|----------|---------------|  
|Unario|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|  
|Binary|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|  
|Conversión (unaria)|`CType`|  
  
 Tenga en cuenta que la `=` en la lista binaria es el operador de comparación, no el operador de asignación.  
  
 Cuando se define `CType`, debe especificar `Widening` o `Narrowing`.  
  
## <a name="matched-pairs"></a>Pares coincidentes  
 Debe definir ciertos operadores como pares coincidentes. Si define un operador de un par de este tipo, debe definir el otro. Los pares correspondientes son los siguientes:  
  
-   `=` y `<>`  
  
-   `>` y `<`  
  
-   `>=` y `<=`  
  
-   `IsTrue` y `IsFalse`  
  
## <a name="data-type-restrictions"></a>Restricciones de tipo de datos  
 Cada operador que define debe implicar la clase o estructura en la que se define. Esto significa que la clase o estructura debe aparecer como el tipo de datos de las acciones siguientes:  
  
-   El operando de un operador unario.  
  
-   Al menos uno de los operandos de un operador binario.  
  
-   El operando o el tipo de valor devuelto de un operador de conversión.  
  
 Ciertos operadores tienen datos adicionales que escriba las restricciones, como se indica a continuación:  
  
-   Si define la `IsTrue` y `IsFalse` operadores, ambos deben devolver el `Boolean` tipo.  
  
-   Si define la `<<` y `>>` operadores, ambos deben especificar el `Integer` escriba para la `operandtype` de `operand2`.  
  
 El tipo de valor devuelto no tiene que corresponda al tipo de alguno de los operandos. Por ejemplo, un operador de comparación como `=` o `<>` puede devolver `Boolean` incluso si ninguno de los operandos es `Boolean`.  
  
## <a name="logical-and-bitwise-operators"></a>Operadores lógicos y bit a bit  
 El `And`, `Or`, `Not`, y `Xor` operadores pueden realizar operaciones lógicas o bit a bit en Visual Basic. Sin embargo, si define uno de estos operadores en una clase o estructura, puede definir solo su operación bit a bit.  
  
 No se puede definir la `AndAlso` operador directamente con un `Operator` instrucción. Sin embargo, puede usar `AndAlso` si se cumplen las condiciones siguientes:  
  
-   Ha definido `And` en los mismos tipos de operando que desea usar para `AndAlso`.  
  
-   La definición de `And` devuelve el mismo tipo que la clase o estructura en la que se ha definido.  
  
-   Ha definido la `IsFalse` operador en la clase o estructura en la que ha definido `And`.  
  
 De forma similar, puede usar `OrElse` si ha definido `Or` en los mismos operandos, se ha definido con el tipo de valor devuelto de la clase o estructura y `IsTrue` en la clase o estructura.  
  
## <a name="widening-and-narrowing-conversions"></a>Widening and Narrowing Conversions  
 A *conversión de ampliación* siempre se realizará correctamente en tiempo de ejecución, mientras que un *conversión de restricción* puede producir un error en tiempo de ejecución. Para obtener más información, consulta [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
 Si declara un procedimiento de conversión como `Widening`, el código de procedimiento no debe generar errores. Esto significa lo siguiente:  
  
-   Siempre debe devolver un valor válido de tipo `type`.  
  
-   Debe controlar todas las excepciones posibles y otras condiciones de error.  
  
-   Deben controlar los errores devueltos desde cualquier procedimiento al que llama.  
  
 Si no hay ninguna posibilidad de que un procedimiento de conversión no se realice correctamente o que TI puede provocar una excepción no controlada, se debe declarar como `Narrowing`.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo de código utiliza el `Operator` instrucción para definir el contorno de una estructura que incluye procedimientos de operador para la `And`, `Or`, `IsFalse`, y `IsTrue` operadores. `And`y `Or` cada toman dos operandos de tipo `abc` y tipo de valor devuelto `abc`. `IsFalse`y `IsTrue` tomar un único operando de tipo `abc` y devolver `Boolean`. Estas definiciones de permitir que el código que realiza la llamada usar `And`, `AndAlso`, `Or`, y `OrElse` con operandos de tipo `abc`.  
  
 [!code-vb[VbVbalrStatements#44](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/operator-statement_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [IsFalse (operador)](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [IsTrue (operador)](../../../visual-basic/language-reference/operators/istrue-operator.md)  
 [Widening](../../../visual-basic/language-reference/modifiers/widening.md)  
 [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [Conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [Definir un operador](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [Definir un operador de conversión](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [Llamar a un procedimiento de operador](../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)  
 [Utilizar una clase que define operadores](../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)

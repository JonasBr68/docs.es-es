---
title: Cadenas interpoladas (Visual Basic)
ms.date: 10/31/2017
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f865d5a7167847bf869d70a39570413dac271a2c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="interpolated-strings-visual-basic-reference"></a>Cadenas interpoladas (referencia de Visual Basic)

Se utiliza para construir cadenas.  Una cadena interpolada es similar a una cadena de plantilla que contiene *expresiones interpoladas*.  Una cadena interpolada devuelve una cadena que reemplaza a las expresiones interpoladas que contiene por sus representaciones de cadena. Esta característica está disponible en Visual Basic 14 y versiones posteriores.

Los argumentos de una cadena interpolada son más fáciles de entender que una [cadena de formato compuesto](../../../../standard/base-types/composite-formatting.md#composite-format-string).  Por ejemplo, la cadena interpolada  
  
```vb  
Console.WriteLine($"Name = {name}, hours = {hours:hh}")
```  
contiene dos expresiones interpoladas, "{name}" y "{hours:hh}". La cadena de formato compuesto equivalente es esta:

```vb
Console.WriteLine("Name = {0}, hours = {1:hh}", name, hours); 
```  

La estructura de una cadena interpolada es la siguiente:  
  
```vb  
$"<text> {<interpolated-expression> [,<field-width>] [:<format-string>] } <text> ..."  
```  

donde: 

- *field-width* es un entero con signo que indica el número de caracteres del campo. Si es positivo, el campo está alineado a la derecha. Si es negativo, está alineado a la izquierda. 

- *format-string* es una cadena de formato adecuada para el tipo de objeto al que se da formato. Por ejemplo, para un <xref:System.DateTime> valor, podría ser un [cadena de formato de fecha y hora estándar](~/docs/standard/base-types/standard-date-and-time-format-strings.md) como "D" o "d".

> [!IMPORTANT]
> No puede haber ningún espacio en blanco entre la `$` y `"` que comienza la cadena. Si lo hace, produce un error del compilador.

 Puede utilizar una cadena interpolada en cualquier lugar que pueda utilizar un literal de cadena.  La cadena interpolada se evalúa cada vez que se ejecuta el código con la cadena interpolada. Esto le permite separar la definición y la evaluación de una cadena interpolada.  
  
 Para incluir una llave ("{" o "}") en una cadena interpolada, use dos llaves, "{{" o "}}".  Consulte la sección Conversiones implícitas para obtener más detalles.  

Si la cadena interpolada contiene otros caracteres con un significado especial en una cadena interpolada, como comillas dobles ("), dos puntos (:) o coma (,), deben incluirse entre caracteres de escape si aparecen en texto literal, o bien deben incluirse en una expresión delimitada por paréntesis si son elementos del lenguaje incluidos en una expresión interpolada. En el ejemplo siguiente las comillas se escriben entre caracteres de escape para incluirlas en la cadena de resultado y se usan paréntesis para delimitar la expresión `(age == 1 ? "" : "s")` de modo que el carácter de dos puntos no se interprete como el principio de una cadena de formato.

[!code-vb[interpolated-strings](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings4.vb)]  

## <a name="implicit-conversions"></a>Conversiones implícitas  

Hay tres conversiones de tipo implícito de una cadena interpolada:  

1. Conversión de una cadena interpolada a <xref:System.String>. En el ejemplo siguiente se devuelve una cadena cuyas expresiones de cadena interpolada se han reemplazado por las representaciones de cadena. Por ejemplo:

   [!code-vb[interpolated-strings1](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings1.vb)]  

   Este es el resultado final de una interpretación de cadena. Todas las apariciones de llaves dobles ("{{" y "}}") se convierten en una única llave. 

2. Conversión de una cadena interpolada a una variable <xref:System.IFormattable> que permite crear varias cadenas de resultado con contenido específico de la referencia cultural de una sola instancia <xref:System.IFormattable>. Esto resulta útil para incluir elementos como los formatos numéricos y de fecha correctos para cada referencia cultural.  Todas las apariciones de llaves dobles ("{{" y "}}") permanecen como llaves dobles hasta que dé formato a la cadena mediante una llamada implícita o explícita al método <xref:System.Object.ToString>.  Todas las expresiones de interpolación incluidas se convierten en {0}, \{1\} y así sucesivamente.  

   En el ejemplo siguiente se usa la reflexión para mostrar los miembros y los valores de propiedad y campo de una variable <xref:System.IFormattable> que se crea a partir de una cadena interpolada. También pasa el <xref:System.IFormattable> variable a la <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> método.

   [!code-vb[interpolated-strings2](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings2.vb)]  

   Tenga en cuenta que la cadena interpolada solo se puede inspeccionar mediante reflexión. Si se pasa a una cadena de método de formato como <xref:System.Console.WriteLine(System.String)>, sus elementos de formato se resuelven y devuelve la cadena de resultado. 

3. Conversión de una cadena interpolada a un <xref:System.FormattableString> variable que representa una cadena de formato compuesto. El hecho de inspeccionar la cadena de formato compuesto y la manera en que se presenta como cadena de resultado podría ayudarle a protegerse frente a un ataque por inyección si estuviese compilando una consulta. Un <xref:System.FormattableString> también incluye:

      - A <xref:System.FormattableString.ToString> sobrecarga que genera una cadena para el <xref:System.Globalization.CultureInfo.CurrentCulture>.
      
      - A <xref:System.FormattableString.Invariant%2A> método que genere una cadena para el <xref:System.Globalization.CultureInfo.InvariantCulture>.
      
      - Un <xref:System.FormattableString.ToString(System.IFormatProvider)> método que genera una cadena de resultado de una referencia cultural especificada. 
  
    Todas las apariciones de llaves dobles ("{{" y "}}") permanecen como llaves dobles hasta que dé formato.  Todas las expresiones de interpolación incluidas se convierten en {0}, \{1\} y así sucesivamente.  

   [!code-vb[interpolated-strings3](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings3.vb)]  

## <a name="see-also"></a>Vea también  
f<xref:System.IFormattable?displayProperty=nameWithType>   
 <xref:System.FormattableString?displayProperty=nameWithType>  
 [Referencia del lenguaje Visual Basic](index.md)  
 
---
title: "Cómo: Recorrer en iteración un árbol de directorio (Guía de programación de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- iterating through folders [C#]
- file iteration [C#]
ms.assetid: c4be4a75-6b1b-46a7-9d38-bab353091ed7
caps.latest.revision: 10
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c63e18bc7e23a9fda4a005745174bdd6c85b3f08
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-iterate-through-a-directory-tree-c-programming-guide"></a>Cómo: Recorrer en iteración un árbol de directorio (Guía de programación de C#)
La frase "recorrer en iteración un árbol de directorios" significa obtener acceso a cada uno de los archivos de todos los subdirectorios anidados bajo una carpeta raíz especificada hasta un nivel de profundidad cualquiera. No es necesario abrir cada archivo. Puede limitarse a recuperar el nombre del archivo o subdirectorio como `string`, o puede recuperar información adicional en forma de un objeto <xref:System.IO.FileInfo?displayProperty=fullName> o <xref:System.IO.DirectoryInfo?displayProperty=fullName>.  
  
> [!NOTE]
>  En Windows, los términos "directorio" y "carpeta" se usan indistintamente. La mayor parte de la documentación y del texto de la interfaz de usuario usa el término "carpeta", pero la biblioteca de clases de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] usa el término "directorio".  
  
 En el caso más simple, en el que sabe con seguridad que tiene permisos de acceso para todos los directorios incluidos en una raíz especificada, puede usar la marca `System.IO.SearchOption.AllDirectories`. Esta marca devuelve todos los subdirectorios anidados que coinciden con el patrón especificado. En el ejemplo siguiente se muestra cómo usar esta marca.  
  
```csharp  
root.GetDirectories("*.*", System.IO.SearchOption.AllDirectories);  
```  
  
 El punto débil de este enfoque es que si uno de los subdirectorios incluidos en la raíz especificada produce una excepción <xref:System.IO.DirectoryNotFoundException> o <xref:System.UnauthorizedAccessException>, se produce un error en todo el método y no devuelve ningún directorio. Lo mismo sucede al usar el método <xref:System.IO.DirectoryInfo.GetFiles%2A>. Si tiene que controlar estas excepciones en subcarpetas específicas, debe recorrer manualmente el árbol de directorios, como se muestra en los ejemplos siguientes.  
  
 Al recorrer manualmente un árbol de directorios, puede controlar primero los subdirectorios (*recorrido en preorden*) o los archivos (*recorrido en postorden*). Al realizar un recorrido en preorden, se recorre todo el árbol bajo la carpeta actual antes de recorrer en iteración los archivos que están directamente en esa carpeta. Los ejemplos que se proporcionan más adelante en este documento realizan un recorrido en postorden, pero puede modificarlos fácilmente para que realicen un recorrido en preorden.  
  
 Otra opción consiste en usar la recursividad o un recorrido basado en la pila. Los ejemplos que se proporcionan más adelante en este documento muestran ambos enfoques.  
  
 Si tiene que realizar diversas operaciones en los archivos y las carpetas, puede dividir estos ejemplos en partes mediante la refactorización de la operación en funciones separadas que se puedan invocar usando un solo delegado.  
  
> [!NOTE]
>  Los sistemas de archivos NTFS pueden contener *puntos de reanálisis* en forma de *puntos de unión*, *vínculos simbólicos* y *vínculos físicos*. Los métodos de .NET Framework como <xref:System.IO.DirectoryInfo.GetFiles%2A> y <xref:System.IO.DirectoryInfo.GetDirectories%2A> no devolverán ningún subdirectorio situado bajo un punto de reanálisis. Este comportamiento protege frente al riesgo de provocar un bucle infinito cuando dos puntos de reanálisis se hacen referencia entre sí. En general, debería ser muy cuidadoso al tratar con puntos de reanálisis para asegurarse de no modificar o eliminar archivos involuntariamente. Si quiere obtener un control preciso de los puntos de reanálisis, use la invocación de plataforma o código nativo para llamar directamente a los métodos de sistema de archivos Win32 adecuados.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo recorrer un árbol de directorios mediante recursividad. El enfoque recursivo resulta elegante, pero puede producir una excepción de desbordamiento de la pila si el árbol de directorios es grande y cuenta con muchos elementos anidados.  
  
 Las excepciones concretas que se controlan y las acciones determinadas que se realizan en cada archivo o carpeta se proporcionan simplemente como ejemplos. Debe modificar este código para que se ajuste a sus requisitos concretos. Para obtener más información, vea los comentarios del código.  
  
 [!code-cs[csFilesandFolders#1](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-iterate-through-a-directory-tree_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo recorrer en iteración los archivos y las carpetas de un árbol de directorios sin usar la recursividad. Esta técnica usa el tipo de colección genérica <xref:System.Collections.Generic.Stack%601>, que es una pila de tipo LIFO (último en entrar, primero en salir).  
  
 Las excepciones concretas que se controlan y las acciones determinadas que se realizan en cada archivo o carpeta se proporcionan simplemente como ejemplos. Debe modificar este código para que se ajuste a sus requisitos concretos. Para obtener más información, vea los comentarios del código.  
  
 [!code-cs[csFilesandFolders#2](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-iterate-through-a-directory-tree_2.cs)]  
  
 Generalmente se tarda mucho tiempo en comprobar cada carpeta para determinar si su aplicación tiene permiso para abrirla. Por consiguiente, el ejemplo de código incluye esa parte de la operación en un bloque `try/catch`. Puede modificar el bloque `catch` de manera que, cuando se le deniegue el acceso a una carpeta, intente elevar sus permisos y obtener acceso a esta de nuevo. Como norma, detecte solamente las excepciones que puede controlar sin dejar la aplicación en un estado desconocido.  
  
 Si debe almacenar el contenido de un árbol de directorios, ya sea en memoria o en el disco, la mejor opción es almacenar solamente la propiedad <xref:System.IO.FileSystemInfo.FullName%2A> (de tipo `string`) para cada archivo. Después, puede usar esta cadena para crear un nuevo objeto <xref:System.IO.FileInfo> o <xref:System.IO.DirectoryInfo>, según sea necesario, o para abrir cualquier archivo que requiera un procesamiento adicional.  
  
## <a name="robust-programming"></a>Programación sólida  
 Un código eficaz de iteración de archivos debe tener en cuenta las numerosas dificultades del sistema de archivos. Para obtener más información, vea [NTFS Technical Reference](http://go.microsoft.com/fwlink/?LinkId=79488).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IO>   
 [LINQ and File Directories](http://msdn.microsoft.com/library/5a5d516c-0279-4a84-ac84-b87f54caa808)  (LINQ y directorios de archivos)  
 [Registro y sistema de archivos (Guía de programación de C#)](../../../csharp/programming-guide/file-system/index.md)
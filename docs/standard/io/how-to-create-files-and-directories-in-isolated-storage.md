---
title: "Cómo: Crear archivos y directorios en almacenamiento aislado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- directories [.NET Framework], isolated storage
- files [.NET Framework], isolated storage
- isolated storage, creating files and directories
- data stores, creating files and directories
- data storage using isolated storage, creating files and directories
- stores, creating files and directories
- storing data using isolated storage, creating files and directories
ms.assetid: 2ca4d2a4-809b-4f00-bc08-bf4a64d3a5c3
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: cf6295e7d58d03e7b4bf4e0a00cfc509d289e071
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-create-files-and-directories-in-isolated-storage"></a>Cómo: Crear archivos y directorios en almacenamiento aislado
Después de haber obtenido un almacén aislado, puede crear directorios y archivos para almacenar los datos. Dentro de un almacén, los nombres de archivos y directorios se especifican con respecto a la raíz del sistema de archivos virtual.  
  
 Para crear un directorio, use el método de instancia <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A?displayProperty=nameWithType>. Si especifica un subdirectorio de un directorio que no existe, se crean dos directorios. Si especifica un directorio que ya existe, el método realiza la devolución sin crear un directorio y no se genera ninguna excepción. Sin embargo, si especifica un nombre de directorio que contiene caracteres no válidos, se produce la excepción <xref:System.IO.IsolatedStorage.IsolatedStorageException>.  
  
 Para crear un archivo, use el método <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateFile%2A?displayProperty=nameWithType>.  
  
 En el sistema operativo Windows, los nombres de archivos y directorios del almacenamiento aislado distinguen mayúsculas y minúsculas. Es decir, si crea un archivo denominado `ThisFile.txt` y luego crea otro archivo llamado `THISFILE.TXT`, solo se crea un archivo. El nombre de archivo mantiene las mayúsculas y minúsculas originales para la presentación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra cómo crear archivos y directorios en un almacén aislado.  
  
 [!code-csharp[Conceptual.IsolatedStorage#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source.cs#1)]
 [!code-vb[Conceptual.IsolatedStorage#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>  
 [Almacenamiento aislado](../../../docs/standard/io/isolated-storage.md)

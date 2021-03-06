---
title: "Cómo: Evitar que una tarea secundaria se adjunte a su elemento primario"
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
- tasks, preventing attachments
ms.assetid: c0fb85d4-9e80-4905-9f65-29acc54201c4
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 2cab2fb9c26a8ddaa868cafebac718e5dfd6baa0
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-prevent-a-child-task-from-attaching-to-its-parent"></a>Cómo: Evitar que una tarea secundaria se adjunte a su elemento primario
En este documento se explica cómo evitar que una tarea secundaria se adjunte a la tarea principal. Impedir que una tarea secundaria se adjunte a su elemento principal es útil cuando se llama a un componente que está escrito por un tercero y que también usa las tareas. Por ejemplo, un componente de terceros que utiliza la opción <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType> para crear un objeto <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> puede causar problemas en el código si es de larga duración o produce una excepción no controlada.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se comparan los efectos del uso de las opciones predeterminadas con los efectos de impedir que una tarea secundaria se adjunte al elemento principal. En el ejemplo se crea un objeto <xref:System.Threading.Tasks.Task> que llama a una biblioteca de terceros que también usa un objeto <xref:System.Threading.Tasks.Task>. La biblioteca de otro fabricante utiliza la opción <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> para crear el objeto <xref:System.Threading.Tasks.Task>. La aplicación utiliza la opción <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> para crear la tarea principal. Esta opción indica el tiempo de ejecución para quitar la especificación <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> de las tareas secundarias.  
  
 [!code-csharp[TPL_DenyChildAttach#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_denychildattach/cs/denychildattach.cs#1)]
 [!code-vb[TPL_DenyChildAttach#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_denychildattach/vb/denychildattach.vb#1)]  
  
 Dado que una tarea primaria no finaliza hasta que finalizan todas las tareas secundarias, una tarea secundaria que se ejecute durante mucho tiempo puede provocar que el rendimiento general de la aplicación sea bajo. En este ejemplo, cuando la aplicación usa las opciones predeterminadas para crear la tarea principal, la tarea secundaria debe finalizar antes de que finalice la principal. Cuando la aplicación utiliza la opción <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType>, el elemento secundario no está asociado al principal. Por lo tanto, la aplicación puede realizar un trabajo adicional después de que finalice la tarea principal y antes debe esperar a que finalice la tarea secundaria.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Copie el código de ejemplo y péguelo en un proyecto de Visual Studio o en un archivo denominado `DenyChildAttach.cs` (`DenyChildAttach.vb` para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) y, a continuación, ejecute el siguiente comando en una ventana del símbolo del sistema de Visual Studio.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe DenyChildAttach.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe DenyChildAttach.vb**  
  
## <a name="robust-programming"></a>Programación sólida  
  
## <a name="see-also"></a>Vea también  
 [Programación asincrónica basada en tareas](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)

---
title: Usar la Biblioteca de clases portable con Model-View-View Model
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
- Portable Class Library [.NET Framework], and MVVM
- MVVM, and Portable Class Library
ms.assetid: 41a0b9f8-15a2-431a-bc35-e310b2953b03
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: cc12a90025a1862fc6c588fe4425f3f8341da313
ms.sourcegitcommit: 91691981897cf8451033cb01071d8f5d94017f97
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2018
---
# <a name="using-portable-class-library-with-model-view-view-model"></a>Usar la Biblioteca de clases portable con Model-View-View Model
Puede utilizar .NET Framework [biblioteca de clases Portable](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) para implementar el modelo Model-View-View Model (MVVM) y compartir los ensamblados en varias plataformas.  
  
 MVVM es un patrón de aplicación que aísla la interfaz de usuario de la lógica empresarial subyacente. Puede implementar el modelo y ver clases del modelo en un [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] proyecto en [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]y, a continuación, crear vistas personalizadas para distintas plataformas. Este enfoque le permite escribir los datos de modelo y lógica de negocios de una sola vez y uso de código de .NET Framework, Silverlight y Windows Phone, y [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] aplicaciones, tal como se muestra en la siguiente ilustración.  
  
 ![Portable con diagrama MVVM](../../../docs/standard/cross-platform/media/portablemvvmdiagram.png "PortableMVVMdiagram")  
  
 En este tema no proporciona información general sobre el patrón MVVM. Solo se proporciona información sobre cómo usar [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] para implementar MVVM. Para obtener más información acerca de MVVM, consulte el [inicio rápido de MVVM](https://msdn.microsoft.com/library/gg430869(v=PandP.40).aspx).  
  
## <a name="classes-that-support-mvvm"></a>Clases que admiten MVVM  
 Si el destino es el [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight y Windows Phone 7.5 para su [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] proyecto, las siguientes clases están disponibles para implementar el patrón MVVM:  
  
-   Clase <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType>  
  
-   Clase <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType>  
  
-   Clase <xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType>  
  
-   Clase <xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType>  
  
-   Clase <xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType>  
  
-   Clase <xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType>  
  
-   Clase <xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType>  
  
-   Clase <xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType>  
  
-   Clase <xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType>  
  
-   Clase <xref:System.Windows.Input.ICommand?displayProperty=nameWithType>  
  
-   Todas las clases en el <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> espacio de nombres  
  
## <a name="implementing-mvvm"></a>Implementar MVVM  
 Para implementar MVVM, crea normalmente el modelo y el modelo de vista en un [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] del proyecto, porque un [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] proyecto no puede hacer referencia a un proyecto no portable. El modelo y el modelo de vista pueden estar en el mismo proyecto o en proyectos independientes. Si utiliza proyectos independientes, agregue una referencia del proyecto de modelo de vista para el proyecto de modelos.  
  
 Después de compilar el modelo y ver los proyectos de modelos, hacer referencia a esos ensamblados en la aplicación que contiene la vista. Si la vista se interactúa con el modelo de vista, basta con hacer referencia al ensamblado que contiene el modelo de vista.  
  
### <a name="model"></a>Modelo  
 En el ejemplo siguiente se muestra una clase de modelo simplificado que puede residir en un [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] proyecto.  
  
 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]  
  
 En el ejemplo siguiente se muestra una manera sencilla de rellenar, recuperar y actualizar los datos en un [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] proyecto. En una aplicación real, puede recuperar los datos de un origen como un servicio de Windows Communication Foundation (WCF).  
  
 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]  
  
### <a name="view-model"></a>Modelo de vista  
 Con frecuencia se agrega una clase base para ver modelos al implementar el patrón MVVM. En el ejemplo siguiente se muestra una clase base.  
  
 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]  
  
 Una implementación de la <xref:System.Windows.Input.ICommand> interfaz es habitual con el patrón MVVM. En el siguiente ejemplo se muestra una implementación de la interfaz <xref:System.Windows.Input.ICommand>.  
  
 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]  
  
 En el ejemplo siguiente se muestra un modelo de vista simplificada.  
  
 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### <a name="view"></a>Ver  
 Desde un [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] aplicación, [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] aplicación, una aplicación basada en Silverlight o aplicación de Windows Phone 7.5, puede hacer referencia al ensamblado que contiene los proyectos de modelo de modelo y vista.  A continuación, cree una vista que interactúa con el modelo de vista. En el ejemplo siguiente se muestra una aplicación de Windows Presentation Foundation (WPF) simplificada que recupera y actualiza los datos desde el modelo de vista. Puede crear vistas similares en Silverlight, Windows Phone, o [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] aplicaciones.  
  
 [!code-xaml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## <a name="see-also"></a>Vea también  
 [Biblioteca de clases portable](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)

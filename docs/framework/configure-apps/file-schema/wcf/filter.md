---
title: '&lt;filtro&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 186c511cd8a69cef5e30e369641628a10a0972d7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltfiltergt"></a>&lt;filtro&gt;

Define un filtro del enrutamiento, que determina el tipo de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] de <xref:System.ServiceModel.Dispatcher.MessageFilter> que se va a utilizar al evaluar los mensajes entrantes, así como cualquier dato o parámetro de compatibilidad requerido por el filtro.

\<system.serviceModel > \<enrutamiento > \<filtros > \<filtro >

## <a name="syntax"></a>Sintaxis

```xml
<routing>
  <filters>
    <filter customType="String" 
            filterData="String" 
            filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath" 
            name="String" />
  </filters>
</routing>
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

| Atributo  | Descripción |
| ---------- | ----------- |
| customType | Cadena que contiene el nombre de tipo completo del tipo personalizado que se va a usar como filtro. Si `filterType` se establece en `custom`, este atributo contiene el nombre de tipo completo de la clase para crear.  `filterData`También se puede contener valores que se usarán durante la evaluación del filtro de tipo personalizado. |
| filterData | Cadena que contiene los datos del filtro. Para obtener más información sobre cómo especificar este atributo, vea <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>. |
| filterType | Cadena que contiene el tipo de filtro. Este atributo es del tipo <xref:System.ServiceModel.Routing.Configuration.FilterType>.  Para obtener más información sobre su funcionamiento con el atributo `filterData`, vea <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>. |
| name       | Cadena que contiene el nombre único de este elemento de filtro. |

### <a name="child-elements"></a>Elementos secundarios

Ninguno.

### <a name="parent-elements"></a>Elementos primarios

| Elemento | Descripción |
| ------- | ----------- |
| [\<enrutamiento >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | Una sección de configuración para definir un conjunto de filtros de enrutamiento, que determina el tipo de [!INCLUDE[ indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter> que se usará al evaluar los mensajes entrantes. |

## <a name="see-also"></a>Vea también

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>    
<xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>   
<xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>   

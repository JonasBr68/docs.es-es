---
title: WCF y WebSockets
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e53b49e-022c-49c7-8984-4b21b53c05b3
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e84bf7a94a6a6fa980e223daf0a6c7aaf489bb6e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="wcf-and-websockets"></a>WCF y WebSockets
.NET Framework 4.5 presenta compatibilidad con WebSockets en Windows Communication Foundation.  WebSockets es una tecnología eficaz basada en estándares que permite la comunicación bidireccional a través de los puertos estándar 80 y 443 de HTTP. El uso de los puertos HTTP estándar permite que WebSockets se comunique a través de la Web mediante intermediarios.  Se han agregado dos nuevos enlaces estándar para admitir la comunicación a través de un transporte WebSocket. <xref:System.ServiceModel.NetHttpBinding> y <xref:System.ServiceModel.NetHttpsBinding>. Se pueden configurar valores específicos de WebSockets en el <xref:System.ServiceModel.Channels.HttpTransportBindingElement> mediante el acceso a la <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> propiedad.
  
## <a name="in-this-section"></a>En esta sección  
 [Uso de NetHttpBinding](../../../../docs/framework/wcf/feature-details/using-the-nethttpbinding.md)  
 Describe <xref:System.ServiceModel.NetHttpBinding> y su configuración.  
  
 [Creación de un servicio WCF que se comunique a través de WebSockets](../../../../docs/framework/wcf/feature-details/how-to-create-a-wcf-service-that-communicates-over-websockets.md)  
 Describe cómo crear un servicio WCF que se comunique a través de Websockets.  
  
## <a name="reference"></a>Referencia  
  
## <a name="related-sections"></a>Secciones relacionadas

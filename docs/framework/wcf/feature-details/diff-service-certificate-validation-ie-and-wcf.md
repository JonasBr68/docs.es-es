---
title: "Diferencias entre la validación de certificados de servicio realizada por Internet Explorer y WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service certificate validation [WCF]
- certificates [WCF], service certificate validation
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 12e30d9df9d6bb0a9f8776099951e4354d302ebf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a>Diferencias entre la validación de certificados de servicio realizada por Internet Explorer y WCF
Debido a la diferencia entre las maneras en que Internet Explorer e [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] validan los certificados del servicio cuando se utilizan HTTPS, es posible que Internet Explorer no pueda tener acceso a la página de Ayuda o el Lenguaje de descripción de servicios Web (WSDL) de un servicio aunque un cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pueda enviar correctamente los mensajes a los extremos de servicio. Esto es porque Internet Explorer comprueba si el certificado del servicio tiene los identificadores de objetos `ServerAuthentication` (OID) en las marcas de uso mejoradas, mientras que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no exige este tipo de restricción. Si Internet Explorer no puede tener acceso a la página de Ayuda del servicio o el WSDL para el servicio, use la [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para tener acceso a los metadatos del servicio.  
  
## <a name="see-also"></a>Vea también  
 [Diferencias en la validación de certificados entre HTTPS, SSL a través de TCP, y seguridad SOAP](../../../../docs/framework/wcf/feature-details/cert-val-diff-https-ssl-over-tcp-and-soap.md)  
 [Recuperación de los metadatos e implementación de un servicio conforme](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)

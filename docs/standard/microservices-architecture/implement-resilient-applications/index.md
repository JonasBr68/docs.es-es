---
title: Implementar aplicaciones resistentes
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Implementar aplicaciones resistentes
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 93e5435b402cc1a8ff049f25465de0f719516f31
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="implementing-resilient-applications"></a>Implementar aplicaciones resistentes

*Sus aplicaciones basadas en microservicios y en la nube deben estar preparadas para los errores parciales que seguramente se acabarán produciendo en algún momento. Debe diseñar su aplicación de modo que sea resistente a estos errores parciales.*

La resistencia es la capacidad de recuperarse de errores y seguir funcionando. No se trata de evitar los errores, sino de aceptar el hecho de que se producirán errores y responder a ellos de forma que se evite el tiempo de inactividad o la pérdida de datos. El objetivo de la resistencia consiste en que la aplicación vuelva a un estado totalmente operativo después de un error.

Es todo un desafío diseñar e implementar una aplicación basada en microservicios. Pero también necesita mantener la aplicación en ejecución en un entorno en el que con seguridad se producirá algún tipo de error. Por lo tanto, la aplicación debe ser resistente. Debe estar diseñada para hacer frente a errores parciales, como las interrupciones de red o el bloqueo de nodos o máquinas virtuales en la nube. Incluso los microservicios (contenedores) que se mueven a otro nodo dentro de un clúster pueden causar breves errores intermitentes dentro de la aplicación.

Los numerosos componentes individuales de la aplicación también deberían incorporar características de seguimiento de estado. Mediante las directrices descritas en este capítulo, podrá crear una aplicación que funcione sin problemas aunque se produzcan tiempos de inactividad transitorios o las interrupciones típicas de las implementaciones complejas y basadas en la nube.


>[!div class="step-by-step"]
[Anterior] (../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md) [Siguiente] (handle-partial-failure.md)

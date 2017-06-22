---
title: "Novedades de Windows Workflow Foundation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WF [WF], novedades"
  - "Windows Workflow Foundation [WF], novedades"
ms.assetid: 11f96014-001e-41a0-bcc2-d0684a52fa43
caps.latest.revision: 29
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 29
---
# Novedades de Windows Workflow Foundation
[!INCLUDE[wf](../../../includes/wf-md.md)] en [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)] cambia varios paradigmas de desarrollo de las versiones anteriores.Los flujos de trabajo son ahora más fáciles de crear, ejecutar, mantener e implementan una amplia gama de nuevas funciones.[!INCLUDE[crabout](../../../includes/crabout-md.md)] migrar las aplicaciones de flujo de trabajo .NET 3.0 y .NET 3.5 a la versión más actual, vea [Guía de migración](../../../docs/framework/windows-workflow-foundation//migration-guidance.md).  
  
## Modelo de la actividad de flujo de trabajo  
 La actividad es ahora la unidad base para crear un flujo de trabajo, en lugar de usar las clases <xref:System.Workflow.Activities.StatemachineWorkflowActivity> o <xref:System.Workflow.Activities.SequentialWorkflowActivity>.La clase <xref:System.Activities.Activity> proporciona la abstracción básica del comportamiento del flujo de trabajo.Los autores de actividad pueden implementar <xref:System.Activities.CodeActivity> para la funcionalidad de actividad personalizada básica o <xref:System.Activities.NativeActivity> para la funcionalidad de actividad personalizada que usa toda la riqueza del runtime.<xref:System.Activities.Activity> es una clase que usan los autores de actividad para expresar nuevos comportamientos mediante declaración en términos de otros objetos <xref:System.Activities.NativeActivity>, <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> o <xref:System.Activities.DynamicActivity> , tanto si están desarrollados de forma personalizada como incluidos en [Biblioteca de actividades integrada](../../../docs/framework/windows-workflow-foundation//net-framework-4-5-built-in-activity-library.md).  
  
## Opciones de actividad compuestas y enriquecidas  
 <xref:System.Activities.Statements.Flowchart> es una nueva actividad eficaz de flujo de control que permite a los autores modelar bucles arbitrarios y bifurcaciones condicionales.<xref:System.Activities.Statements.Flowchart> proporciona un modelo de programación controlado por eventos que anteriormente solo se podía implementar con <xref:System.Workflow.Activities.StateMachineWorkflowActivity>.Los flujos de trabajo de procedimiento se benefician de las nuevas actividades de control de flujo que modelan las estructuras de control de flujo tradicionales, como <xref:System.Activities.Statements.TryCatch> y <xref:System.Activities.Statements.Switch%601>.  
  
## Biblioteca de actividades integrada y expandida  
 Las nuevas características de la biblioteca de actividades incluyen:  
  
-   Nuevas actividades de control de flujo: <xref:System.Activities.Statements.DoWhile>, <xref:System.Activities.Statements.Pick>, <xref:System.Activities.Statements.TryCatch>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.Switch%601> y <xref:System.Activities.Statements.ParallelForEach%601>.  
  
-   Actividades para manipular los datos de miembros, como <xref:System.Activities.Statements.Assign> y actividades de colección como <xref:System.Activities.Statements.AddToCollection%601>.  
  
-   Actividades para controlar las transacciones, como <xref:System.Activities.Statements.TransactionScope> y <xref:System.Activities.Statements.Compensate>.  
  
-   Nuevas actividades de mensajería como <xref:System.ServiceModel.Activities.SendContent> y <xref:System.ServiceModel.Activities.ReceiveReply>.  
  
## Modelo de datos de actividad explícito  
 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] incluye las nuevas opciones para almacenar o mover los datos.Se pueden almacenar datos en una actividad usando <xref:System.Activities.Variable>.Al mover datos hacia dentro de una actividad y fuera de ella, los tipos de argumento especializados se usan para determinar la dirección en la que se están moviendo los datos.Estos tipos son <xref:System.Activities.InArgument>, <xref:System.Activities.InOutArgument> y <xref:System.Activities.OutArgument>.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Modelo de datos de Windows Workflow Foundation](../../../docs/framework/windows-workflow-foundation//data-model.md).  
  
## Hospedaje, persistencia y opciones de seguimiento mejoradas  
 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] contiene mejoras de persistencia como las siguientes:  
  
-   Hay más opciones para ejecutar los flujos de trabajo, incluidas <xref:System.ServiceModel.Activities.WorkflowServiceHost>, <xref:System.Activities.WorkflowApplication> y <xref:System.Activities.WorkflowInvoker>.  
  
-   Se pueden conservar explícitamente los datos de estado del flujo de trabajo mediante la actividad <xref:System.Activities.Statements.Persist>.  
  
-   Un host puede conservar un <xref:System.Activities.ActivityInstance> sin descargarlo.  
  
-   Los flujos de trabajo pueden especificar zonas sin conservación mientras trabajan con datos que no se pueden conservar, de manera que la persistencia se posponga hasta que salga la zona sin conservación.  
  
-   Las transacciones se pueden fluir en un flujo de trabajo mediante <xref:System.Activities.Statements.TransactionScope>.  
  
-   El seguimiento puede llevarse a cabo de una forma más sencilla con <xref:System.Activities.Tracking.TrackingParticipant>.  
  
-   Se proporciona el seguimiento del registro de eventos del sistema mediante <xref:System.Activities.Tracking.EtwTrackingParticipant>.  
  
-   Actualmente, reanudar un flujo de trabajo pendiente se administra mediante un objeto <xref:System.Activities.Bookmark>.  
  
## Mejor capacidad para ampliar la experiencia de diseñador de WF  
 El nuevo diseñador de WF se compila en [!INCLUDE[avalon1](../../../includes/avalon1-md.md)] y proporciona un modelo más fácil de utilizar cuando se vuelve a hospedar el diseñador de WF fuera de Visual Studio. Además, también proporciona mecanismos más sencillos para crear diseñadores de actividades personalizados.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Personalizar la experiencia de diseño del flujo de trabajo](../../../docs/framework/windows-workflow-foundation//customizing-the-workflow-design-experience.md).
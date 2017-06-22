---
title: ".NET Framework Performance | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "performance [.NET Framework]"
  - "reliability [.NET Framework]"
ms.assetid: c1676cca-3f1a-41ec-b469-9029566074fc
caps.latest.revision: 20
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 20
---
# .NET Framework Performance
Si desea crear aplicaciones que exhiban un gran rendimiento, debe diseñar y planear ese rendimiento al igual que hace con cualquier otra característica de la aplicación.  Puede usar las herramientas proporcionadas por Microsoft para medir el rendimiento de su aplicación y, en caso necesario, realizar mejoras en el uso de la memoria, el rendimiento del código y la respuesta.  En este tema se enumeran las herramientas de análisis de rendimiento ofrecidas por Microsoft, y se proporcionan vínculos a otros temas que abordan el rendimiento en áreas específicas del desarrollo de aplicaciones.  
  
## Diseñar y planear el rendimiento  
 Si desea que su aplicación tenga un gran rendimiento, diséñelo en la aplicación como haría con cualquier otra característica.  Determine los escenarios críticos de rendimiento de la aplicación, establezca objetivos y, desde un principio, mida frecuentemente el rendimiento en estos escenarios de la aplicación.  Dado que cada aplicación es diferente y tiene distintas rutas de ejecución críticas para el rendimiento, determinar esas rutas desde un inicio y centrar los esfuerzos permite maximizar la productividad.  
  
 No hace falta estar totalmente familiarizado con la plataforma de destino para crear una aplicación de alto rendimiento.  Sin embargo, es necesario entender las partes de la plataforma de destino que suponen un mayor coste en términos de rendimiento.  Esto se puede hacer si se mide el rendimiento desde el principio del proceso de desarrollo.  
  
 Para determinar las áreas que son cruciales para el rendimiento y establecer los objetivos correspondientes, tenga siempre en cuenta la experiencia de usuario.  El tiempo de inicio y la respuesta son dos áreas clave que influirán en la percepción que el usuario tendrá de su aplicación.  Si su aplicación usa mucha memoria, puede parecer lenta para el usuario o afectar al resto de aplicaciones que se ejecutan en el sistema; en algunos casos, podría no aprobar el proceso de envío de la Tienda Windows o de la Tienda de Windows Phone.  Además, si determina las partes del código que se ejecutan con mayor frecuencia, podrá asegurarse de que esas partes estén bien optimizadas.  
  
## Analizar el rendimiento  
 Como parte del plan de desarrollo general, establezca momentos del desarrollo en los que mida el rendimiento de la aplicación y compare los resultados con los objetivos definidos previamente.  Mida la aplicación en el entorno y el hardware que espera que tengan los usuarios.  Un análisis temprano y frecuente del rendimiento de la aplicación puede influir en las decisiones sobre arquitectura que podrían resultar caras de corregir en un momento posterior del ciclo de desarrollo.  En las secciones siguientes se describen las herramientas de rendimiento que se pueden usar para analizar las aplicaciones y se aborda el seguimiento de eventos utilizado por estas herramientas.  
  
### Herramientas de rendimiento  
 Estas son algunas de las herramientas de rendimiento que puede usar con sus aplicaciones de .NET Framework.  
  
|Herramienta|Descripción|  
|-----------------|-----------------|  
|Análisis de rendimiento de Visual Studio|Sirve para analizar el uso de CPU de las aplicaciones de .NET Framework que se implementarán en equipos que ejecuten el sistema operativo Windows.<br /><br /> Esta herramienta está disponible en el menú **Depurar** de Visual Studio después de abrir un proyecto.  Para obtener más información, consulte [Uso de las herramientas de generación de perfiles](../Topic/Performance%20Explorer.md). **Note:**  Use el análisis de aplicación de Windows Phone \(vea la fila siguiente\) si la aplicación está diseñada para Windows Phone.|  
|Análisis de aplicación de Windows Phone|Sirve para analizar la CPU y la memoria, la velocidad de transferencia de datos de red, la respuesta de la aplicación y el consumo de batería en las aplicaciones de Windows Phone.<br /><br /> Esta herramienta está disponible en el menú **Depurar** de un proyecto de Windows Phone de Visual Studio después de instalar el [SDK de Windows Phone](http://go.microsoft.com/fwlink/?LinkId=265773).  Para obtener más información, consulte [Generación de perfiles de aplicaciones para Windows Phone](http://msdn.microsoft.com/library/windowsphone/develop/jj215908\(v=vs.105\).aspx).|  
|[PerfView](http://www.microsoft.com/download/details.aspx?id=28567)|Sirve para identificar problemas de rendimiento relacionados con la CPU y la memoria.  Esta herramienta usa seguimiento de eventos para Windows \(ETW\) y API de generación de perfiles de CLR para ofrecer análisis avanzados de CPU y memoria, así como información sobre la recolección de elementos no utilizados y la compilación JIT.  Para obtener más información sobre cómo usar PerfView, vea el tutorial y los archivos de ayuda que están incluidos en la aplicación, los [tutoriales en vídeo de Channel 9](http://channel9.msdn.com/Series/PerfView-Tutorial) y las [entradas de blog](http://blogs.msdn.com/b/vancem/archive/tags/perfview/).<br /><br /> Para problemas de memoria más específicos, vea el artículo sobre el [uso de PerfView para examinar la memoria](http://channel9.msdn.com/Series/PerfView-Tutorial/PerfView-Tutorial-9-NET-Memory-Investigation-Basics-of-GC-Heap-Snapshots).|  
|[Windows Performance Analyzer](http://www.microsoft.com/download/details.aspx?id=30652)|Sirve para determinar el rendimiento general del sistema; por ejemplo, el uso de memoria y almacenamiento de la aplicación cuando se ejecutan varias aplicaciones en el mismo equipo.  Esta herramienta está disponible en el centro de descargas como parte de Windows Assessment and Deployment Kit \(ADK\) para [!INCLUDE[win8](../../../includes/win8-md.md)].  Para más información, vea el artículo sobre [Windows Performance Analyzer](http://msdn.microsoft.com/library/windows/desktop/hh448170.aspx).|  
  
### Seguimiento de eventos para Windows \(ETW\)  
 ETW es una técnica que permite obtener información de diagnóstico sobre el código que se ejecuta y es esencial para muchas de las herramientas de rendimiento mencionadas anteriormente.  ETW crea registros cuando se generan determinados eventos en las aplicaciones de .NET Framework y Windows.  Con ETW, puede habilitar y deshabilitar el registro dinámicamente, de modo que puede realizar un seguimiento detallado en un entorno de producción sin necesidad de reiniciar la aplicación.  .NET Framework admite eventos de ETW y ETW es utilizado por muchas herramientas de rendimiento y generación de perfiles para crear datos sobre rendimiento.  A menudo, estas herramientas habilitan y deshabilitan eventos de ETW, por lo que resulta útil estar familiarizado con ellas.  Puede usar eventos de ETW específicos para recopilar información de rendimiento sobre componentes concretos de la aplicación.  Para obtener más información acerca de la compatibilidad ETW en .NET Framework, consulte [ETW Events in the Common Language Runtime](../../../docs/framework/performance/etw-events-in-the-common-language-runtime.md) y [Eventos ETW en Task Parallel Library y PLINQ](../../../docs/framework/performance/etw-events-in-task-parallel-library-and-plinq.md).  
  
## Rendimiento por tipo de aplicación  
 Cada tipo de aplicación de .NET Framework tiene sus propios procedimientos recomendados, consideraciones y herramientas para evaluar el rendimiento.  En la tabla siguiente se ofrecen los vínculos a temas sobre rendimiento para tipos de aplicación de .NET Framework.  
  
|Tipo de aplicación|Vea|  
|------------------------|---------|  
|Aplicaciones de .NET Framework para todas las plataformas|[Garbage Collection and Performance](../../../docs/standard/garbage-collection/performance.md)<br /><br /> [Sugerencias para mejorar el rendimiento](../../../docs/framework/performance/performance-tips.md)|  
|Aplicaciones de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] escritas en C\+\+, C\# y Visual Basic|[Procedimientos recomendados de rendimiento para aplicaciones de la Tienda Windows con C\+\+, C\# y Visual Basic](http://msdn.microsoft.com/library/windows/apps/hh750313.aspx)|  
|Windows Phone|[Consideraciones sobre el rendimiento de aplicaciones para Windows Phone](http://msdn.microsoft.com/library/windowsphone/develop/ff967560\(v=vs.105\).aspx)<br /><br /> [Análisis de aplicación de Windows Phone](http://msdn.microsoft.com/library/windowsphone/develop/hh202934\(v=vs.105\).aspx)<br /><br /> [Publique sus aplicaciones para Windows Phone más rápido en Marketplace](http://msdn.microsoft.com/magazine/hh781024.aspx)|  
|Windows Presentation Foundation \(WPF\)|[WPF Performance Suite](../Topic/WPF%20Performance%20Suite.md)|  
|Silverlight|[Sugerencias sobre rendimiento](http://msdn.microsoft.com/library/cc189071\(v=vs.95\).aspx)|  
|ASP.NET|[ASP.NET Performance Overview](../Topic/ASP.NET%20Performance%20Overview.md)|  
|Windows Forms|[Sugerencias prácticas para aumentar el rendimiento de aplicaciones de Windows Forms](http://msdn.microsoft.com/magazine/cc163630.aspx)|  
  
## Temas relacionados  
  
|Título|Descripción|  
|------------|-----------------|  
|[Caching in .NET Framework Applications](../../../docs/framework/performance/caching-in-net-framework-applications.md)|Información sobre las técnicas para almacenar datos en la caché a fin de mejorar el rendimiento de la aplicación.|  
|[Lazy Initialization](../../../docs/framework/performance/lazy-initialization.md)|Información sobre cómo inicializar objetos según sea necesario para mejorar el rendimiento, en concreto al inicio de la aplicación.|  
|[Reliability](../../../docs/framework/performance/reliability.md)|Información sobre cómo evitar excepciones asincrónicas en un entorno de servidor.|  
|[Escribir aplicaciones grandes de .NET Framework que respondan](../../../docs/framework/performance/writing-large-responsive-apps.md)|Sugerencias sobre rendimiento que proceden de reescribir los compiladores de C\# y Visual Basic en código administrado; además, se incluyen varios ejemplos reales del compilador de C\#.|
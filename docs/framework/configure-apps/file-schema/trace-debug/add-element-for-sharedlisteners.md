---
title: '&lt;agregar&gt; (elemento) para &lt;sharedListeners&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <sharedListeners>
- add element for <sharedListeners>
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: 490e58d4514667c5ec781dd76644012b0c97509d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-element-for-ltsharedlistenersgt"></a>&lt;agregar&gt; (elemento) para &lt;sharedListeners&gt;
Agrega un agente de escucha a la colección `sharedListeners`. `sharedListeners`es una colección de agentes de escucha que cualquier [ \<origen >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) o [ \<seguimiento >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md) pueden hacer referencia.  De forma predeterminada, los agentes de escucha en el `sharedListeners` colección no se colocan en un `Listeners` colección. Deben agregarse por el nombre a la [ \<origen >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) o [ \<seguimiento >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md). No es posible obtener los agentes de escucha el `sharedListeners` colección en el código en tiempo de ejecución.  
  
 \<configuration>  
\<System.Diagnostics >  
\<sharedListeners > elemento  
\<add>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`name`|Atributo necesario.<br /><br /> Especifica el nombre del agente de escucha que se utiliza para agregar el agente de escucha compartido a un `Listeners` colección.|  
|`type`|Atributo necesario.<br /><br /> Especifica el tipo del agente de escucha. Debe utilizar una cadena que cumpla los requisitos especificados en [especificar nombres de tipo completos](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Atributo opcional.<br /><br /> La cadena pasada al constructor de la clase especificada.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<filter>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-sharedlisteners.md)|Agrega un filtro a un agente de escucha en la colección `sharedListeners`.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.|  
|`sharedListeners`|Una colección de agentes de escucha que se puede hacer referencia a cualquier origen o elemento de seguimiento.|  
  
## <a name="remarks"></a>Comentarios  
 Las clases de agente de escucha incluidas en .NET Framework se derivan de la <xref:System.Diagnostics.TraceListener> clase. El valor de la `name` atributo se utiliza para agregar el agente de escucha compartido a un `Listeners` colección para un seguimiento o un origen de seguimiento. El valor de la `initializeData` atributo depende del tipo de escucha que se cree. No todos los agentes de escucha de seguimiento requieren que se especifiquen `initializeData`.  
  
> [!NOTE]
>  Cuando se usa el `initializeData` atributo, es posible que obtenga el compilador advertencia "no se declaró el atributo 'initializeData'". Esta advertencia se produce porque los valores de configuración se validan con la clase base abstracta <xref:System.Diagnostics.TraceListener>, que no reconoce el `initializeData` atributo. Por lo general, puede omitir esta advertencia para las implementaciones de agente de escucha de seguimiento que tiene un constructor que toma un parámetro.  
  
 En la tabla siguiente muestra los agentes de escucha de seguimiento que se incluyen con .NET Framework y se describe el valor de sus `initializeData` atributos.  
  
|Clase de agente de escucha de seguimiento|valor del atributo initializeData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|El `useErrorStream` valor para el <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.  Establecer el `initializeData` atribuir a "`true`"escribir trace y debug de salida en el flujo de error estándar; establézcala en"`false`" para escribir en el flujo de salida estándar.|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|El nombre del archivo de la <xref:System.Diagnostics.DelimitedListTraceListener> escribe en.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|El nombre de un origen de registro de eventos existente.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|El nombre del archivo que el <xref:System.Diagnostics.EventSchemaTraceListener> escribe en.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|El nombre del archivo que el <xref:System.Diagnostics.TextWriterTraceListener> escribe en.|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|El nombre del archivo que el <xref:System.Diagnostics.XmlWriterTraceListener> escribe en.|  
  
## <a name="configuration-file"></a>Archivo de configuración  
 Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de aplicación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar `<add>` elementos que se va a agregar el <xref:System.Diagnostics.TextWriterTraceListener> `textListener` a la `sharedListeners` colección.   `textListener`se agrega por el nombre a la `Listeners` colección para el origen de seguimiento `TraceSourceApp`. La `textListener` agente de escucha escribe la salida de seguimiento en el archivo myListener.log.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"   
        type="System.Diagnostics.TextWriterTraceListener"   
        initializeData="myListener.log"/>  
    </sharedListeners>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Diagnostics.TraceSource>  
 <xref:System.Diagnostics.TraceListener>  
 [Esquema de la configuración de seguimiento y depuración](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [Agentes de escucha de seguimiento](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)

---
title: Elemento personalizado para NameValueSectionHandler y DictionarySectionHandler
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords: custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a9722493ec62952d7cbc07d478687b8495d24f95
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="a2eae-102">Elemento personalizado para NameValueSectionHandler y DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="a2eae-102">Custom element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="a2eae-103">Define los valores de las secciones de configuración personalizada que utilizan el <xref:System.Configuration.NameValueSectionHandler> y <xref:System.Configuration.DictionarySectionHandler> clases.</span><span class="sxs-lookup"><span data-stu-id="a2eae-103">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span>

<span data-ttu-id="a2eae-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="a2eae-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="a2eae-105">&nbsp;&nbsp;**\<sectionName >**</span><span class="sxs-lookup"><span data-stu-id="a2eae-105">&nbsp;&nbsp;**\<sectionName>**</span></span>

## <a name="attributes"></a><span data-ttu-id="a2eae-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="a2eae-106">Attributes</span></span>

<span data-ttu-id="a2eae-107">Ninguna</span><span class="sxs-lookup"><span data-stu-id="a2eae-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="a2eae-108">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="a2eae-108">Parent element</span></span>

|     | <span data-ttu-id="a2eae-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="a2eae-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="a2eae-110">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="a2eae-110">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="a2eae-111">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a2eae-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="a2eae-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a2eae-112">Child elements</span></span>

|     | <span data-ttu-id="a2eae-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="a2eae-113">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="a2eae-114">[**\<Agregar >** ](~/docs/framework/configure-apps/file-schema/add-element-for-custom-2.md) para <xref:System.Configuration.NameValueSectionHandler> y<xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="a2eae-114">[**\<add>**](~/docs/framework/configure-apps/file-schema/add-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span>  | <span data-ttu-id="a2eae-115">Agrega la configuración de aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="a2eae-115">Adds custom application settings.</span></span> |
| <span data-ttu-id="a2eae-116">[**\<Quitar >** ](~/docs/framework/configure-apps/file-schema/remove-element-for-custom-2.md) para <xref:System.Configuration.NameValueSectionHandler> y<xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="a2eae-116">[**\<remove>**](~/docs/framework/configure-apps/file-schema/remove-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> |    <span data-ttu-id="a2eae-117">Quita un valor definido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a2eae-117">Removes a previously defined setting.</span></span> |
| <span data-ttu-id="a2eae-118">[**\<Borrar >** ](~/docs/framework/configure-apps/file-schema/clear-element-for-custom-2.md) para <xref:System.Configuration.NameValueSectionHandler> y<xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="a2eae-118">[**\<clear>**](~/docs/framework/configure-apps/file-schema/clear-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="a2eae-119">Borra todos los valores definidos anteriormente en una sección.</span><span class="sxs-lookup"><span data-stu-id="a2eae-119">Clears all previously defined settings in a section.</span></span> |

## <a name="remarks"></a><span data-ttu-id="a2eae-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a2eae-120">Remarks</span></span>

<span data-ttu-id="a2eae-121">El  **\<sectionName >** trata de un elemento personalizado definido por una  **\<sección >** etiqueta en el  **\<configSections >**elemento.</span><span class="sxs-lookup"><span data-stu-id="a2eae-121">The **\<sectionName>** element is a custom element defined by a **\<section>** tag in the **\<configSections>** element.</span></span>

<span data-ttu-id="a2eae-122">En la tabla siguiente se muestra que el tipo de objeto al método ConfigurationSettings.GetConfig devuelve para cada controlador de la sección de configuración:</span><span class="sxs-lookup"><span data-stu-id="a2eae-122">The following table shows the type of object the ConfigurationSettings.GetConfig method returns for each configuration section handler:</span></span>

| <span data-ttu-id="a2eae-123">Controlador de la sección de configuración</span><span class="sxs-lookup"><span data-stu-id="a2eae-123">Configuration section handler</span></span>                        | <span data-ttu-id="a2eae-124">Tipo devuelto</span><span class="sxs-lookup"><span data-stu-id="a2eae-124">Return type</span></span>                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a><span data-ttu-id="a2eae-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a2eae-125">Example</span></span>

<span data-ttu-id="a2eae-126">En el ejemplo siguiente se muestra cómo declarar las secciones que utilizan el <xref:System.Configuration.DictionarySectionHandler> y <xref:System.Configuration.NameValueSectionHandler> clases.</span><span class="sxs-lookup"><span data-stu-id="a2eae-126">The following example shows how to declare sections that use the <xref:System.Configuration.DictionarySectionHandler> and <xref:System.Configuration.NameValueSectionHandler> classes.</span></span> 

<span data-ttu-id="a2eae-127">El primer elemento personalizado es  **\<dictionarySample >**, que contiene los valores leídos por el <xref:System.Configuration.DictionarySectionHandler> clase en la `System.dll` ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a2eae-127">The first custom element is **\<dictionarySample>**, which contains settings read by the <xref:System.Configuration.DictionarySectionHandler> class in the `System.dll` assembly.</span></span> <span data-ttu-id="a2eae-128">El segundo elemento personalizado es  **\<mySection >**, que contiene los valores leídos por el <xref:System.Configuration.NameValueSectionHandler> clase en la `System.dll` ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a2eae-128">The second custom element is **\<mySection>**, which contains settings read by the <xref:System.Configuration.NameValueSectionHandler> class in the `System.dll` assembly.</span></span>

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
    <sectionGroup name="mySectionGroup">
      <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="a2eae-129">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="a2eae-129">Configuration file</span></span>

<span data-ttu-id="a2eae-130">Este elemento se puede usar en el archivo de configuración de aplicación, archivo de configuración de máquina (*Machine.config*), y *Web.config* archivos que no están en el nivel de directorio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a2eae-130">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="a2eae-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2eae-131">See also</span></span>

[<span data-ttu-id="a2eae-132">Esquema de archivos de configuración de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a2eae-132">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
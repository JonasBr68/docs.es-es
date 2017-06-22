---
title: "Enlace de datos y LINQ to DataSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 310bff4a-32dd-4f20-a271-6dbd82912631
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Enlace de datos y LINQ to DataSet
*Enlace de datos* es el proceso que establece una conexión entre la interfaz de usuario de la aplicación y la lógica de negocios.  Si el enlace está configurado correctamente y los datos proporcionan la notificaciones adecuadas, al cambiar los valores de los datos, los elementos enlazados a los mismos reflejarán de manera automática dichos cambios.  <xref:System.Data.DataSet> es una representación de datos residente en memoria que proporciona un modelo de programación relacional coherente independientemente del origen de datos que contiene.  <xref:System.Data.DataView> de ADO.NET 2.0 permite ordenar y filtrar los datos almacenados en <xref:System.Data.DataTable>.  Esta funcionalidad se utiliza con frecuencia en aplicaciones de enlace de datos.  Mediante <xref:System.Data.DataView> puede exponer los datos de una tabla con distintos criterios de ordenación y filtrar los datos por el estado de fila o basándose en una expresión de filtro.  Para obtener más información sobre del objeto <xref:System.Data.DataView>, vea [DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] permite a los programadores crear consultas complejas y eficaces en <xref:System.Data.DataSet> utilizando [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)].  No obstante, una consulta [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] devuelve una enumeración de objetos <xref:System.Data.DataRow>, que no se usa con facilidad en un caso de enlace. Para facilitar el proceso de enlace, se puede crear un objeto <xref:System.Data.DataView> a partir de una consulta [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].  Este objeto <xref:System.Data.DataView> usa el filtrado y la ordenación especificados en la consulta, pero es más adecuado para el enlace de datos.  [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] amplía la funcionalidad del objeto <xref:System.Data.DataView> proporcionando filtrado y ordenación basados en expresiones de [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)], lo que permite operaciones de filtrado y ordenación mucho más complejas y eficaces que las basadas en cadenas.  
  
 Observe que <xref:System.Data.DataView> representa la propia consulta y no es una vista encima de la consulta.  <xref:System.Data.DataView> se enlaza a un control de la interfaz de usuario, como <xref:System.Windows.Forms.DataGrid> o <xref:System.Windows.Forms.DataGridView>, proporcionando un modelo de enlace de datos simple.  <xref:System.Data.DataView> se puede crear también a partir de <xref:System.Data.DataTable>, proporcionando una vista predeterminada de esa tabla.  
  
## En esta sección  
 [Crear un objeto DataView](../../../../docs/framework/data/adonet/creating-a-dataview-object-linq-to-dataset.md)  
 Proporciona información sobre creación de <xref:System.Data.DataView>.  
  
 [Filtrar con DataView](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md)  
 Describe cómo filtrar con <xref:System.Data.DataView>.  
  
 [Ordenar con DataView](../../../../docs/framework/data/adonet/sorting-with-dataview-linq-to-dataset.md)  
 Describe cómo ordenar con <xref:System.Data.DataView>.  
  
 [Consultar la colección DataRowView en un objeto DataView](../../../../docs/framework/data/adonet/querying-the-datarowview-collection-in-a-dataview.md)  
 Proporciona información sobre cómo consultar la colección <xref:System.Data.DataRowView> expuesta por <xref:System.Data.DataView>.  
  
 [Rendimiento DataView](../../../../docs/framework/data/adonet/dataview-performance.md)  
 Proporciona información sobre <xref:System.Data.DataView> y rendimiento.  
  
 [Cómo enlazar un objeto DataView al control DataGridView de Windows Forms](../../../../docs/framework/data/adonet/how-to-bind-a-dataview-object-to-a-winforms-datagridview-control.md)  
 Describe cómo enlazar un objeto <xref:System.Data.DataView> a <xref:System.Windows.Forms.DataGridView>.  
  
## Vea también  
 [Guía de programación](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)
---
title: "Directrices y opciones de tecnología de ADO.NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c8577281-38e6-4ce5-b036-572039a4c3d8
caps.latest.revision: "6"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: aa4cefb27ff3fde3f4f31d996a80b19b94ea57e2
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="adonet-technology-options-and-guidelines"></a>Directrices y opciones de tecnología de ADO.NET
La plataforma de datos ADO.NET es una estrategia para varias versiones mediante la cual se reduce la cantidad de código y el mantenimiento que necesitan los programadores con el fin de poder programar en modelos de datos de entidades conceptuales. Esta plataforma incluye ADO.NET Entity Framework y tecnologías relacionadas.  
  
## <a name="entity-framework"></a>Entity Framework  
 ADO.NET Entity Framework está diseñado para permitir que los desarrolladores creen aplicaciones de acceso a los datos programando en un modelo de aplicación conceptual en lugar de programar directamente en un esquema de almacenamiento relacional. El objetivo es reducir la cantidad de código y mantenimiento que se necesita para las aplicaciones orientadas a datos. Para obtener más información, consulte [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md).  
  
### <a name="entity-data-model-edm"></a>Entity Data Model (EDM)  
 Entity Data Model (EDM) es una especificación de diseño que define datos de aplicación como conjuntos de entidades y relaciones. Los datos de este modelo admiten la asignación relacional de objetos y la capacidad de programación de los datos entre los límites de aplicación.  
  
### <a name="object-services"></a>Servicios de objeto  
 Los servicios de objeto permiten a los programadores interactuar con los modelos conceptuales a través de un conjunto de clases de Common Language Runtime (CLR). Estas clases se pueden generar de manera automática desde el modelo conceptual o se pueden desarrollar de manera independiente para reflejar la estructura del modelo conceptual. Los servicios de objeto también proporcionan compatibilidad de infraestructura con Entity Framework, con servicios como administración de estados, seguimiento de cambios, resolución de identidad, relaciones de carga y navegación, propagación de cambios de objeto a modificaciones de base de datos y compatibilidad de creación de consultas para Entity SQL. Para más información, vea [Información general de Servicios de objeto (Entity Framework)](http://msdn.microsoft.com/library/43014cf9-c9cb-4538-bfbb-197820b60038).  
  
### <a name="linq-to-entities"></a>LINQ to Entities  
 LINQ to Entities es una implementación de Language-Integrated Query (LINQ) que permite a los desarrolladores crear consultas fuertemente tipadas en el contexto de objeto de Entity Framework mediante expresiones de LINQ y operadores de consulta estándar de LINQ. LINQ to Entities permite a los programadores trabajar con un modelo conceptual con una asignación de objetos relacionales entre bases de datos de Microsoft SQL Server y de terceros. Para obtener más información, consulte [LINQ to Entities](../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md).  
  
### <a name="entity-sql"></a>Entity SQL  
 Entity SQL es un lenguaje de consulta basado en texto diseñado para interactuar con un Entity Data Model. Entity SQL es un dialecto de SQL que contiene construcciones para la consulta en términos de conceptos de creación de patrones de nivel superior, como herencia, tipos complejos y relaciones explícitas. Los programadores pueden utilizar también Entity SQL directamente con los servicios de objetos. Para obtener más información, consulte [lenguaje Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md).  
  
### <a name="entityclient"></a>EntityClient  
 EntityClient es un nuevo proveedor de datos .NET Framework utilizado para interactuar con un Entity Data Model. EntityClient sigue el patrón de proveedor de datos .NET Framework de exponer objetos <xref:System.Data.EntityClient.EntityConnection> y <xref:System.Data.EntityClient.EntityCommand> que devuelven <xref:System.Data.EntityClient.EntityDataReader>. EntityClient funciona con el lenguaje Entity SQL, que proporciona una asignación flexible a los proveedores de datos específicos de almacenamiento. Para obtener más información, consulte [EntityClient y Entity SQL](http://msdn.microsoft.com/library/49202ab9-ac98-4b4b-a05c-140e422bf527).  
  
### <a name="entity-data-model-tools"></a>Herramientas de Entity Data Model  
 Entity Framework proporciona herramientas de línea de comandos, asistentes y diseñadores para facilitar la compilación de aplicaciones EDM. El control EntityDataSource admite casos de enlace de datos basándose en el EDM. La superficie de programación del control EntityDataSource es similar a otros controles de origen de datos de Visual Studio. Para obtener más información, consulte [ADO.NET Entity Data Model Tools](http://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527).  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 LINQ to SQL es una implementación relacional de objetos (OR/M) que le permite modelar una base de datos de SQL Server mediante las clases de .NET Framework. Además, le permite consultar la base de datos usando LINQ, así como actualizar, insertar y eliminar datos. LINQ to SQL admite transacciones, vistas y procedimientos almacenados, proporcionando una forma fácil de integrar la validación de datos y las reglas de la lógica de negocios en el modelo de datos. Puede usar Object Relational Designer (O/R Designer) para modelar clases de entidad y asociaciones basadas en los objetos de una base de datos. Para obtener más información, vea [LINQ to SQL Tools en Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).  
  
## <a name="wcf-data-services"></a>Servicios de datos de WCF  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] implementa servicios de datos en web o en una intranet. Los datos se estructuran como entidades y relaciones de acuerdo a las especificaciones de Entity Data Model. Los datos implementados en este modelo se pueden direccionar mediante el protocolo HTTP estándar. Para obtener más información, consulte [4.5 de servicios de datos de WCF](../../../../docs/framework/data/wcf/index.md).  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)  
 [Novedades de ADO.NET](../../../../docs/framework/data/adonet/whats-new.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)

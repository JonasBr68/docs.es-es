---
title: "Semántica de comparación (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: e20d47e0ae97067d2dcafcf929f717598d4e3e80
ms.sourcegitcommit: 96cc82cac4650adfb65ba351506d8a8fbcd17b5c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2018
---
# <a name="comparison-semantics-entity-sql"></a>Semántica de comparación (Entity SQL)
El uso de cualquiera de los operadores de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] siguientes implica la comparación de las instancias de tipo:  
  
## <a name="explicit-comparison"></a>Comparación explícita  
 Operaciones de igualdad:  
  
-   =  
  
-   !=  
  
 Operaciones de ordenación:  
  
-   <  
  
-   \<=  
  
-   \>  
  
-   \>=  
  
 Operaciones de nulabilidad:  
  
-   IS NULL  
  
-   IS NOT NULL  
  
## <a name="explicit-distinction"></a>Distinción explícita  
 Distinción de igualdad:  
  
-   DISTINCT  
  
-   GROUP BY  
  
 Distinción de ordenación:  
  
-   ORDER BY  
  
## <a name="implicit-distinction"></a>Distinción implícita  
 Operaciones y predicados de conjuntos (igualdad):  
  
-   UNION  
  
-   INTERSECT  
  
-   EXCEPT  
  
-   SET  
  
-   OVERLAPS  
  
 Predicados de elementos (igualdad):  
  
-   IN  
  
## <a name="supported-combinations"></a>Combinaciones admitidas  
 En la tabla siguiente se muestran todas las combinaciones admitidas de los operadores de comparación para cada clase de tipo:  
  
|**Type**|**=**<br /><br /> **!=**|**GROUP BY**<br /><br /> **DISTINCT**|**UNION**<br /><br /> **INTERSECT**<br /><br /> **EXCEPT**<br /><br /> **SET**<br /><br /> **OVERLAPS**|**IN**|**<   <=**<br /><br /> **>   >=**|**ORDER BY**|**ES NULL**<br /><br /> **NO ES NULO**|  
|-|-|-|-|-|-|-|-|  
|Tipo de entidad|Ref<sup>1</sup>|Todas las propiedades<sup>2</sup>|Todas las propiedades<sup>2</sup>|Todas las propiedades<sup>2</sup>|Iniciar<sup>3</sup>|Iniciar<sup>3</sup>|Ref<sup>1</sup>|  
|Tipo complejo|Iniciar<sup>3</sup>|Iniciar<sup>3</sup>|Iniciar<sup>3</sup>|Iniciar<sup>3</sup>|Iniciar<sup>3</sup>|Iniciar<sup>3</sup>|Iniciar<sup>3</sup>|  
|Fila|Todas las propiedades<sup>4</sup>|Todas las propiedades<sup>4</sup>|Todas las propiedades<sup>4</sup>|Iniciar<sup>3</sup>|Iniciar<sup>3</sup>|Todas las propiedades<sup>4</sup>|Iniciar<sup>3</sup>|  
|Tipo primitivo|Depende del proveedor|Depende del proveedor|Depende del proveedor|Depende del proveedor|Depende del proveedor|Depende del proveedor|Depende del proveedor|  
|Conjunto múltiple|Iniciar<sup>3</sup>|Iniciar<sup>3</sup>|Iniciar<sup>3</sup>|Iniciar<sup>3</sup>|Iniciar<sup>3</sup>|Iniciar<sup>3</sup>|Iniciar<sup>3</sup>|  
|Ref|Sí<sup>5</sup>|Sí<sup>5</sup>|Sí<sup>5</sup>|Sí<sup>5</sup>|Throw|Throw|Sí<sup>5</sup>|  
|Asociación<br /><br /> type|Iniciar<sup>3</sup>|Throw|Throw|Throw|Iniciar<sup>3</sup>|Iniciar<sup>3</sup>|Iniciar<sup>3</sup>|  
  
 <sup>1</sup>las referencias de las instancias del tipo de entidad dado se comparan implícitamente, como se muestra en el ejemplo siguiente:  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 Una instancia de entidad no se puede comparar con una referencia explícita. Si se intenta, se inicia una excepción. Por ejemplo, la siguiente consulta iniciaría una excepción:  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <sup>2</sup>propiedades de tipos complejos se simplifican antes de enviarse al almacén, por lo que lleguen a ser comparables (siempre que todas sus propiedades sean comparables). Consulte también <sup>4.</sup>  
  
 <sup>3</sup>en tiempo de ejecución de Entity Framework detecta un caso no admitido y se inicia una excepción significativa sin activar el proveedor o almacén.  
  
 <sup>4</sup>se realiza un intento para comparar todas las propiedades. Si hay una propiedad que es de un tipo no comparable, como text, ntext o image, se podría iniciar una excepción de servidor.  
  
 <sup>5</sup>se comparan todos los elementos individuales de las referencias (Esto incluye el nombre del conjunto de entidades y todas las propiedades claves del tipo de entidad).  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)

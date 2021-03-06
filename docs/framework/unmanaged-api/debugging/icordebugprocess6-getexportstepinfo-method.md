---
title: "Método ICorDebugProcess6::GetExportStepInfo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d3c69bbc904f54636e56be6d235d1070b9fecf1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess6getexportstepinfo-method"></a>Método ICorDebugProcess6::GetExportStepInfo
Proporciona información sobre las funciones exportadas en tiempo de ejecución para ayudar a recorrer el código administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,   
    [out] CorDebugCodeInvokeKind* pInvokeKind,   
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
#### <a name="parameters"></a>Parámetros  
 pszExportName  
 [in] Nombre de una función de exportación en tiempo de ejecución según aparece escrito en la tabla de exportación de PE.  
  
 invokeKind  
 [out] Un puntero a un miembro de la [CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md) enumeración que describe cómo la función exportada va a invocar código administrado.  
  
 invokePurpose  
 [out] Un puntero a un miembro de la [CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md) enumeración que describe por qué la función exportada llamará a código administrado.  
  
## <a name="return-value"></a>Valor devuelto  
 El método puede devolver los valores enumerados en la siguiente tabla.  
  
|Valor devuelto|Descripción|  
|------------------|-----------------|  
|`S_OK`|La llamada al método se realizó correctamente.|  
|`E_POINTER`|`pInvokeKind`o `pInvokePurpose` es **null**.|  
|Otros valores de error de `HRESULT`.|Según el caso.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorDebugProcess6 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

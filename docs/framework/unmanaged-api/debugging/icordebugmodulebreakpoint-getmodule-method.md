---
title: "ICorDebugModuleBreakpoint::GetModule (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModuleBreakpoint.GetModule
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModuleBreakpoint::GetModule
helpviewer_keywords:
- ICorDebugModuleBreakpoint::GetModule method [.NET Framework debugging]
- GetModule method, ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: ffd5d9ec-4564-4200-b625-b306eec0ebd7
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: afdd16cbdb2b33ad0806fbce1dab5e6d7130fb0c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodulebreakpointgetmodule-method"></a><span data-ttu-id="af921-102">ICorDebugModuleBreakpoint::GetModule (Método)</span><span class="sxs-lookup"><span data-stu-id="af921-102">ICorDebugModuleBreakpoint::GetModule Method</span></span>
<span data-ttu-id="af921-103">Obtiene un puntero de interfaz a un "ICorDebugModule" que hace referencia el módulo en el que se ha establecido este punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="af921-103">Gets an interface pointer to an "ICorDebugModule" that references the module in which this breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af921-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af921-104">Syntax</span></span>  
  
```  
HRESULT GetModule (  
    [out] ICorDebugModule   **ppModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="af921-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="af921-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="af921-106">[out] Un puntero a la dirección de un `ICorDebugModule` interfaz que hace referencia al módulo en el que se establece el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="af921-106">[out] A pointer to the address of an `ICorDebugModule` interface that references the module in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af921-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="af921-107">Requirements</span></span>  
 <span data-ttu-id="af921-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af921-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af921-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af921-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af921-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af921-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af921-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af921-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af921-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="af921-112">See Also</span></span>  
 
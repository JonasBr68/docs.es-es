---
title: "IObjectHandle::Unwrap (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IObjectHandle.Unwrap
api_location: mscoree.dll
api_type: COM
f1_keywords: Unwrap
helpviewer_keywords:
- Unwrap method [.NET Framework hosting]
- IObjectHandle::Unwrap method [.NET Framework hosting]
ms.assetid: 794c6f8e-ed58-416b-b756-e864f2c958f7
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5d4ff12674fefbde6afbbe76cb411dbbe33d2187
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="iobjecthandleunwrap-method"></a><span data-ttu-id="265c9-102">IObjectHandle::Unwrap (Método)</span><span class="sxs-lookup"><span data-stu-id="265c9-102">IObjectHandle::Unwrap Method</span></span>
<span data-ttu-id="265c9-103">Desencapsula un objeto de cálculo de referencias por valor de direccionamiento indirecto.</span><span class="sxs-lookup"><span data-stu-id="265c9-103">Unwraps a marshal-by-value object from indirection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="265c9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="265c9-104">Syntax</span></span>  
  
```  
HRESULT Unwrap (  
    [out, retval] VARIANT *ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="265c9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="265c9-105">Parameters</span></span>  
 `ppv`  
 <span data-ttu-id="265c9-106">[out] Un puntero al objeto desempaquetarse.</span><span class="sxs-lookup"><span data-stu-id="265c9-106">[out] A pointer to the object to be unwrapped.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="265c9-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="265c9-107">Requirements</span></span>  
 <span data-ttu-id="265c9-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="265c9-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="265c9-109">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="265c9-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="265c9-110">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="265c9-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="265c9-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="265c9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="265c9-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="265c9-112">See Also</span></span>  
 
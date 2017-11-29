---
title: "ICorPublishProcessEnum::Next (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishProcessEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishProcessEnum::Next
helpviewer_keywords:
- ICorPublishProcessEnum::Next method [.NET Framework debugging]
- Next method, ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: 6c399f37-1e38-4ca1-b70d-8ae41f7228b7
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6823a8d973b997576da3271c85234b347f1c8562
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorpublishprocessenumnext-method"></a><span data-ttu-id="cfcfc-102">ICorPublishProcessEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="cfcfc-102">ICorPublishProcessEnum::Next Method</span></span>
<span data-ttu-id="cfcfc-103">Obtiene el número especificado de procesos de la colección, comenzando en la posición actual del cursor.</span><span class="sxs-lookup"><span data-stu-id="cfcfc-103">Gets the specified number of processes from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfcfc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cfcfc-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorPublishProcess **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cfcfc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cfcfc-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="cfcfc-106">[in] El número de procesos que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="cfcfc-106">[in] The number of processes to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="cfcfc-107">[out] Recupera un puntero a la matriz de [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objetos, cada uno de los cuales representa un proceso.</span><span class="sxs-lookup"><span data-stu-id="cfcfc-107">[out] A pointer to the array of retrieved [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects, each of which represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="cfcfc-108">[out] Puntero al número de procesos realmente devueltos.</span><span class="sxs-lookup"><span data-stu-id="cfcfc-108">[out] Pointer to the number of processes actually returned.</span></span> <span data-ttu-id="cfcfc-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="cfcfc-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfcfc-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cfcfc-110">Requirements</span></span>  
 <span data-ttu-id="cfcfc-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cfcfc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfcfc-112">**Encabezado:** Cordebug.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="cfcfc-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="cfcfc-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cfcfc-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cfcfc-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfcfc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfcfc-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="cfcfc-115">See Also</span></span>  
 [<span data-ttu-id="cfcfc-116">ICorPublishProcessEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cfcfc-116">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)
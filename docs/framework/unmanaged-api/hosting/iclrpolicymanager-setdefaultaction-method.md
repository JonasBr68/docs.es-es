---
title: "ICLRPolicyManager::SetDefaultAction (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRPolicyManager.SetDefaultAction
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRPolicyManager::SetDefaultAction
helpviewer_keywords:
- SetDefaultAction method [.NET Framework hosting]
- ICLRPolicyManager::SetDefaultAction method [.NET Framework hosting]
ms.assetid: f9411e7a-27df-451f-9f6c-d643d6a7a7ce
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ecc2e35433a1021e230b45adddf3bede055d3dfd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclrpolicymanagersetdefaultaction-method"></a><span data-ttu-id="4f0f6-102">ICLRPolicyManager::SetDefaultAction (Método)</span><span class="sxs-lookup"><span data-stu-id="4f0f6-102">ICLRPolicyManager::SetDefaultAction Method</span></span>
<span data-ttu-id="4f0f6-103">Especifica la acción de directiva que common language runtime (CLR) debe realizar cuando se produzca la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="4f0f6-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f0f6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4f0f6-104">Syntax</span></span>  
  
```  
HRESULT SetDefaultAction (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4f0f6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4f0f6-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="4f0f6-106">[in] Uno de los [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) valores, que indica la acción para que CLR se debe personalizar el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="4f0f6-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the action for which CLR behavior should be customized.</span></span>  
  
 `action`  
 <span data-ttu-id="4f0f6-107">[in] Uno de los [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valores, que indica la acción de directiva que el CLR debe tomar cuando `operation` se produce.</span><span class="sxs-lookup"><span data-stu-id="4f0f6-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4f0f6-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4f0f6-108">Return Value</span></span>  
  
|<span data-ttu-id="4f0f6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4f0f6-109">HRESULT</span></span>|<span data-ttu-id="4f0f6-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="4f0f6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4f0f6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4f0f6-111">S_OK</span></span>|<span data-ttu-id="4f0f6-112">`SetDefaultAction`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="4f0f6-112">`SetDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="4f0f6-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4f0f6-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4f0f6-114">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="4f0f6-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4f0f6-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4f0f6-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4f0f6-116">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="4f0f6-116">The call timed out.</span></span>|  
|<span data-ttu-id="4f0f6-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4f0f6-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4f0f6-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="4f0f6-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4f0f6-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4f0f6-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4f0f6-120">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="4f0f6-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4f0f6-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4f0f6-121">E_FAIL</span></span>|<span data-ttu-id="4f0f6-122">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="4f0f6-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4f0f6-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="4f0f6-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4f0f6-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4f0f6-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4f0f6-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4f0f6-125">E_INVALIDARG</span></span>|<span data-ttu-id="4f0f6-126">No es válida `action` no se especificó para el `operation`, o se ha proporcionado un valor no válido para `operation`.</span><span class="sxs-lookup"><span data-stu-id="4f0f6-126">An invalid `action` was specified for the `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f0f6-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4f0f6-127">Remarks</span></span>  
 <span data-ttu-id="4f0f6-128">No todos los valores de acción de directiva se pueden especificar como el comportamiento predeterminado para las operaciones de CLR.</span><span class="sxs-lookup"><span data-stu-id="4f0f6-128">Not all policy action values can be specified as the default behavior for CLR operations.</span></span> <span data-ttu-id="4f0f6-129">`SetDefaultAction`Normalmente se usa solo para intensificar el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="4f0f6-129">`SetDefaultAction` can typically be used only to escalate behavior.</span></span> <span data-ttu-id="4f0f6-130">Por ejemplo, un host puede especificar que las anulaciones de subprocesos se conviertan en anulaciones anulaciones de subprocesos, pero no se especifique lo contrario.</span><span class="sxs-lookup"><span data-stu-id="4f0f6-130">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="4f0f6-131">La siguiente tabla describe los válido `action` valores para cada posible `operation` valor.</span><span class="sxs-lookup"><span data-stu-id="4f0f6-131">The table below describes the valid `action` values for each possible `operation` value.</span></span>  
  
|<span data-ttu-id="4f0f6-132">Valor de`operation`</span><span class="sxs-lookup"><span data-stu-id="4f0f6-132">Value for `operation`</span></span>|<span data-ttu-id="4f0f6-133">Valores válidos para`action`</span><span class="sxs-lookup"><span data-stu-id="4f0f6-133">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="4f0f6-134">OPR_ThreadAbort</span><span class="sxs-lookup"><span data-stu-id="4f0f6-134">OPR_ThreadAbort</span></span>|<span data-ttu-id="4f0f6-135">-eAbortThread</span><span class="sxs-lookup"><span data-stu-id="4f0f6-135">-   eAbortThread</span></span><br /><span data-ttu-id="4f0f6-136">-eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="4f0f6-136">-   eRudeAbortThread</span></span><br /><span data-ttu-id="4f0f6-137">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="4f0f6-137">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="4f0f6-138">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="4f0f6-138">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="4f0f6-139">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="4f0f6-139">-   eExitProcess</span></span><br /><span data-ttu-id="4f0f6-140">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="4f0f6-140">-   eFastExitProcess</span></span><br /><span data-ttu-id="4f0f6-141">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="4f0f6-141">-   eRudeExitProcess</span></span><br /><span data-ttu-id="4f0f6-142">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="4f0f6-142">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="4f0f6-143">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="4f0f6-143">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="4f0f6-144">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="4f0f6-144">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="4f0f6-145">-eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="4f0f6-145">-   eRudeAbortThread</span></span><br /><span data-ttu-id="4f0f6-146">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="4f0f6-146">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="4f0f6-147">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="4f0f6-147">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="4f0f6-148">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="4f0f6-148">-   eExitProcess</span></span><br /><span data-ttu-id="4f0f6-149">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="4f0f6-149">-   eFastExitProcess</span></span><br /><span data-ttu-id="4f0f6-150">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="4f0f6-150">-   eRudeExitProcess</span></span><br /><span data-ttu-id="4f0f6-151">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="4f0f6-151">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="4f0f6-152">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="4f0f6-152">OPR_AppDomainUnload</span></span>|<span data-ttu-id="4f0f6-153">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="4f0f6-153">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="4f0f6-154">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="4f0f6-154">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="4f0f6-155">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="4f0f6-155">-   eExitProcess</span></span><br /><span data-ttu-id="4f0f6-156">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="4f0f6-156">-   eFastExitProcess</span></span><br /><span data-ttu-id="4f0f6-157">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="4f0f6-157">-   eRudeExitProcess</span></span><br /><span data-ttu-id="4f0f6-158">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="4f0f6-158">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="4f0f6-159">OPR_AppDomainRudeUnload</span><span class="sxs-lookup"><span data-stu-id="4f0f6-159">OPR_AppDomainRudeUnload</span></span>|<span data-ttu-id="4f0f6-160">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="4f0f6-160">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="4f0f6-161">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="4f0f6-161">-   eExitProcess</span></span><br /><span data-ttu-id="4f0f6-162">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="4f0f6-162">-   eFastExitProcess</span></span><br /><span data-ttu-id="4f0f6-163">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="4f0f6-163">-   eRudeExitProcess</span></span><br /><span data-ttu-id="4f0f6-164">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="4f0f6-164">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="4f0f6-165">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="4f0f6-165">OPR_ProcessExit</span></span>|<span data-ttu-id="4f0f6-166">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="4f0f6-166">-   eExitProcess</span></span><br /><span data-ttu-id="4f0f6-167">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="4f0f6-167">-   eFastExitProcess</span></span><br /><span data-ttu-id="4f0f6-168">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="4f0f6-168">-   eRudeExitProcess</span></span><br /><span data-ttu-id="4f0f6-169">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="4f0f6-169">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="4f0f6-170">OPR_FinalizerRun</span><span class="sxs-lookup"><span data-stu-id="4f0f6-170">OPR_FinalizerRun</span></span>|<span data-ttu-id="4f0f6-171">-eNoAction</span><span class="sxs-lookup"><span data-stu-id="4f0f6-171">-   eNoAction</span></span><br /><span data-ttu-id="4f0f6-172">-eAbortThread</span><span class="sxs-lookup"><span data-stu-id="4f0f6-172">-   eAbortThread</span></span><br /><span data-ttu-id="4f0f6-173">-eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="4f0f6-173">-   eRudeAbortThread</span></span><br /><span data-ttu-id="4f0f6-174">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="4f0f6-174">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="4f0f6-175">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="4f0f6-175">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="4f0f6-176">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="4f0f6-176">-   eExitProcess</span></span><br /><span data-ttu-id="4f0f6-177">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="4f0f6-177">-   eFastExitProcess</span></span><br /><span data-ttu-id="4f0f6-178">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="4f0f6-178">-   eRudeExitProcess</span></span><br /><span data-ttu-id="4f0f6-179">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="4f0f6-179">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4f0f6-180">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4f0f6-180">Requirements</span></span>  
 <span data-ttu-id="4f0f6-181">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f0f6-181">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f0f6-182">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4f0f6-182">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4f0f6-183">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4f0f6-183">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4f0f6-184">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f0f6-184">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f0f6-185">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f0f6-185">See Also</span></span>  
 [<span data-ttu-id="4f0f6-186">EClrOperation (enumeración)</span><span class="sxs-lookup"><span data-stu-id="4f0f6-186">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="4f0f6-187">EPolicyAction (enumeración)</span><span class="sxs-lookup"><span data-stu-id="4f0f6-187">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="4f0f6-188">ICLRPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4f0f6-188">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
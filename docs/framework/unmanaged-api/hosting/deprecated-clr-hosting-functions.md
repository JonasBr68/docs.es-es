---
title: Funciones de hospedaje de CLR en desuso
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9530fecb4f2ca6f59d165e49c282320966fd2fa8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="deprecated-clr-hosting-functions"></a><span data-ttu-id="9860c-102">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="9860c-102">Deprecated CLR Hosting Functions</span></span>
<span data-ttu-id="9860c-103">Esta sección describen las funciones estáticas globales no administradas que utiliza versiones anteriores de la API de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="9860c-103">This section describes the unmanaged global static functions that earlier versions of the hosting API used.</span></span>  
  
 <span data-ttu-id="9860c-104">Con la excepción de las funciones de infraestructura (`_Cor*` funciones), que se usa únicamente con .NET Framework, estas funciones han quedado obsoletas en la [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9860c-104">With the exception of the infrastructure functions (`_Cor*` functions), which are used only by the .NET Framework, these functions have been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="activation-functions"></a><span data-ttu-id="9860c-105">Funciones de activación</span><span class="sxs-lookup"><span data-stu-id="9860c-105">Activation functions</span></span>  
 [<span data-ttu-id="9860c-106">ClrCreateManagedInstance (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-106">ClrCreateManagedInstance Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/clrcreatemanagedinstance-function.md)  
 <span data-ttu-id="9860c-107">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-107">Deprecated.</span></span> <span data-ttu-id="9860c-108">Crea una instancia del tipo administrado especificado.</span><span class="sxs-lookup"><span data-stu-id="9860c-108">Creates an instance of the specified managed type.</span></span>  
  
 [<span data-ttu-id="9860c-109">CoInitializeCor (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-109">CoInitializeCor Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializecor-function.md)  
 <span data-ttu-id="9860c-110">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="9860c-110">Obsolete.</span></span> <span data-ttu-id="9860c-111">Para inicializar common language runtime (CLR), use [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="9860c-111">To initialize the common language runtime (CLR), use either [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span>  
  
 [<span data-ttu-id="9860c-112">CoInitializeEE (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-112">CoInitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)  
 <span data-ttu-id="9860c-113">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-113">Deprecated.</span></span> <span data-ttu-id="9860c-114">Garantiza que el motor de ejecución de CLR se carga en un proceso.</span><span class="sxs-lookup"><span data-stu-id="9860c-114">Ensures that the CLR execution engine is loaded into a process.</span></span> <span data-ttu-id="9860c-115">Use la [ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="9860c-115">Use the [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method instead.</span></span>  
  
 [<span data-ttu-id="9860c-116">CorBindToCurrentRuntime (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-116">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 <span data-ttu-id="9860c-117">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-117">Deprecated.</span></span> <span data-ttu-id="9860c-118">Carga common language runtime (CLR) en un proceso usando la información de versión almacenada en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="9860c-118">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span>  
  
 [<span data-ttu-id="9860c-119">CorBindToRuntime (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-119">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 <span data-ttu-id="9860c-120">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-120">Deprecated.</span></span> <span data-ttu-id="9860c-121">Permite que los hosts no administrados cargar CLR en un proceso.</span><span class="sxs-lookup"><span data-stu-id="9860c-121">Enables unmanaged hosts to load the CLR into a process.</span></span>  
  
 [<span data-ttu-id="9860c-122">CorBindToRuntimeByCfg (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-122">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 <span data-ttu-id="9860c-123">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-123">Deprecated.</span></span> <span data-ttu-id="9860c-124">Carga el CLR en un proceso mediante el uso de información de versión que se lee desde un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="9860c-124">Loads the CLR into a process by using version information that is read from an XML file.</span></span>  
  
 [<span data-ttu-id="9860c-125">CorBindToRuntimeEx (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-125">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 <span data-ttu-id="9860c-126">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-126">Deprecated.</span></span> <span data-ttu-id="9860c-127">Permite a los hosts no administrados cargar CLR en un proceso y permite establecer marcas para especificar el comportamiento de CLR.</span><span class="sxs-lookup"><span data-stu-id="9860c-127">Enables unmanaged hosts to load the CLR into a process, and allows you to set flags to specify the behavior of the CLR.</span></span>  
  
 [<span data-ttu-id="9860c-128">CorBindToRuntimeHost (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 <span data-ttu-id="9860c-129">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-129">Deprecated.</span></span> <span data-ttu-id="9860c-130">Permite a los hosts cargar una versión especificada de CLR en un proceso.</span><span class="sxs-lookup"><span data-stu-id="9860c-130">Enables hosts to load a specified version of the CLR into a process.</span></span>  
  
 [<span data-ttu-id="9860c-131">GetCORRequiredVersion (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-131">GetCORRequiredVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getcorrequiredversion-function.md)  
 <span data-ttu-id="9860c-132">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-132">Deprecated.</span></span> <span data-ttu-id="9860c-133">Obtiene el número de versión CLR necesario.</span><span class="sxs-lookup"><span data-stu-id="9860c-133">Gets the required CLR version number.</span></span>  
  
 [<span data-ttu-id="9860c-134">GetCORSystemDirectory (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-134">GetCORSystemDirectory Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md)  
 <span data-ttu-id="9860c-135">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-135">Deprecated.</span></span> <span data-ttu-id="9860c-136">Devuelve el directorio de instalación de CLR que se carga en el proceso.</span><span class="sxs-lookup"><span data-stu-id="9860c-136">Returns the installation directory of the CLR that is loaded into the process.</span></span>  
  
 [<span data-ttu-id="9860c-137">GetRealProcAddress (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-137">GetRealProcAddress Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md)  
 <span data-ttu-id="9860c-138">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-138">Deprecated.</span></span> <span data-ttu-id="9860c-139">Obtiene la dirección de la función especificada que se exporta desde la última versión instalada de CLR.</span><span class="sxs-lookup"><span data-stu-id="9860c-139">Gets the address of the specified function that is exported from the latest installed version of the CLR.</span></span>  
  
 [<span data-ttu-id="9860c-140">GetRequestedRuntimeInfo (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-140">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 <span data-ttu-id="9860c-141">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-141">Deprecated.</span></span> <span data-ttu-id="9860c-142">Obtiene información de versión y directorio acerca del entorno CLR solicitado por una aplicación.</span><span class="sxs-lookup"><span data-stu-id="9860c-142">Gets version and directory information about the CLR requested by an application.</span></span>  
  
## <a name="clr-version-functions"></a><span data-ttu-id="9860c-143">Funciones de la versión CLR</span><span class="sxs-lookup"><span data-stu-id="9860c-143">CLR version functions</span></span>  
 <span data-ttu-id="9860c-144">Las funciones de esta sección devuelven una versión CLR; no activa el CLR.</span><span class="sxs-lookup"><span data-stu-id="9860c-144">The functions in this section return a CLR version; they do not activate the CLR.</span></span>  
  
 [<span data-ttu-id="9860c-145">GetCORVersion (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-145">GetCORVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getcorversion-function.md)  
 <span data-ttu-id="9860c-146">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-146">Deprecated.</span></span> <span data-ttu-id="9860c-147">Devuelve el número de versión de CLR que se ejecuta en el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="9860c-147">Returns the version number of the CLR that is running in the current process.</span></span>  
  
 [<span data-ttu-id="9860c-148">GetFileVersion (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-148">GetFileVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md)  
 <span data-ttu-id="9860c-149">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-149">Deprecated.</span></span> <span data-ttu-id="9860c-150">Obtiene la información de versión CLR del archivo especificado, utilizando el búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="9860c-150">Gets the CLR version information of the specified file, using the specified buffer.</span></span>  
  
 [<span data-ttu-id="9860c-151">GetRequestedRuntimeVersion (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-151">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 <span data-ttu-id="9860c-152">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-152">Deprecated.</span></span> <span data-ttu-id="9860c-153">Obtiene el número de versión de CLR solicitado por la aplicación especificada.</span><span class="sxs-lookup"><span data-stu-id="9860c-153">Gets the version number of the CLR requested by the specified application.</span></span> <span data-ttu-id="9860c-154">Si no está instalada esa versión, obtiene la versión más reciente que esté instalada antes de la versión solicitada.</span><span class="sxs-lookup"><span data-stu-id="9860c-154">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 [<span data-ttu-id="9860c-155">GetRequestedRuntimeVersionForCLSID (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-155">GetRequestedRuntimeVersionForCLSID Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversionforclsid-function.md)  
 <span data-ttu-id="9860c-156">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-156">Deprecated.</span></span> <span data-ttu-id="9860c-157">Obtiene la información de versión CLR correspondiente para la clase con el CLSID especificado.</span><span class="sxs-lookup"><span data-stu-id="9860c-157">Gets the appropriate CLR version information for the class with the specified CLSID.</span></span>  
  
 [<span data-ttu-id="9860c-158">GetVersionFromProcess (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-158">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)  
 <span data-ttu-id="9860c-159">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-159">Deprecated.</span></span> <span data-ttu-id="9860c-160">Obtiene el número de versión de CLR que está asociado con el identificador de proceso especificado.</span><span class="sxs-lookup"><span data-stu-id="9860c-160">Gets the version number of the CLR that is associated with the specified process handle.</span></span>  
  
 [<span data-ttu-id="9860c-161">LockClrVersion (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-161">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)  
 <span data-ttu-id="9860c-162">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-162">Deprecated.</span></span> <span data-ttu-id="9860c-163">Permite al host determinar qué versión de CLR se utilizará en el proceso antes de inicializar el CLR de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="9860c-163">Allows the host to determine which version of the CLR will be used within the process before explicitly initializing the CLR.</span></span>  
  
## <a name="hosting-functions"></a><span data-ttu-id="9860c-164">Funciones de hospedaje</span><span class="sxs-lookup"><span data-stu-id="9860c-164">Hosting functions</span></span>  
 [<span data-ttu-id="9860c-165">CallFunctionShim (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-165">CallFunctionShim Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/callfunctionshim-function.md)  
 <span data-ttu-id="9860c-166">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-166">Deprecated.</span></span> <span data-ttu-id="9860c-167">Realiza una llamada a la función que tiene el nombre especificado y los parámetros en la biblioteca especificada.</span><span class="sxs-lookup"><span data-stu-id="9860c-167">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 [<span data-ttu-id="9860c-168">CoEEShutDownCOM (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-168">CoEEShutDownCOM Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coeeshutdowncom-function.md)  
 <span data-ttu-id="9860c-169">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-169">Deprecated.</span></span> <span data-ttu-id="9860c-170">Descarga un ensamblado COM del proceso.</span><span class="sxs-lookup"><span data-stu-id="9860c-170">Unloads a COM assembly from the process.</span></span>  
  
 [<span data-ttu-id="9860c-171">CorExitProcess (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-171">CorExitProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)  
 <span data-ttu-id="9860c-172">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-172">Deprecated.</span></span> <span data-ttu-id="9860c-173">Se cierra el proceso actual no administrado.</span><span class="sxs-lookup"><span data-stu-id="9860c-173">Shuts down the current unmanaged process.</span></span>  
  
 [<span data-ttu-id="9860c-174">CorLaunchApplication (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-174">CorLaunchApplication Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corlaunchapplication-function.md)  
 <span data-ttu-id="9860c-175">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-175">Deprecated.</span></span> <span data-ttu-id="9860c-176">Inicia la aplicación en la ruta de acceso de red especificada, utilizando los manifiestos especificados y otros datos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="9860c-176">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 [<span data-ttu-id="9860c-177">CorMarkThreadInThreadPool (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-177">CorMarkThreadInThreadPool Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/cormarkthreadinthreadpool-function.md)  
 <span data-ttu-id="9860c-178">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-178">Deprecated.</span></span> <span data-ttu-id="9860c-179">Marca el subproceso actualmente en ejecución del grupo de subprocesos para la ejecución de código administrado.</span><span class="sxs-lookup"><span data-stu-id="9860c-179">Marks the currently executing thread-pool thread for the execution of managed code.</span></span> <span data-ttu-id="9860c-180">A partir de la versión 2.0 de .NET Framework, esta función no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="9860c-180">Starting with the .NET Framework version 2.0, this function has no effect.</span></span> <span data-ttu-id="9860c-181">No es necesario y puede quitarse desde el código.</span><span class="sxs-lookup"><span data-stu-id="9860c-181">It is not required, and can be removed from your code.</span></span>  
  
 [<span data-ttu-id="9860c-182">CoUninitializeCor (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-182">CoUninitializeCor Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)  
 <span data-ttu-id="9860c-183">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="9860c-183">Obsolete.</span></span> <span data-ttu-id="9860c-184">El CLR no se puede descargar desde un proceso.</span><span class="sxs-lookup"><span data-stu-id="9860c-184">The CLR cannot be unloaded from a process.</span></span>  
  
 [<span data-ttu-id="9860c-185">CoUninitializeEE (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-185">CoUninitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md)  
 <span data-ttu-id="9860c-186">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="9860c-186">Obsolete.</span></span>  
  
 [<span data-ttu-id="9860c-187">CreateDebuggingInterfaceFromVersion (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-187">CreateDebuggingInterfaceFromVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md)  
 <span data-ttu-id="9860c-188">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-188">Deprecated.</span></span> <span data-ttu-id="9860c-189">Crea un [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) objeto basándose en la información de versión especificada.</span><span class="sxs-lookup"><span data-stu-id="9860c-189">Creates an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 [<span data-ttu-id="9860c-190">CreateICeeFileGen (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-190">CreateICeeFileGen Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md)  
 <span data-ttu-id="9860c-191">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-191">Deprecated.</span></span> <span data-ttu-id="9860c-192">Crea un [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="9860c-192">Creates an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="9860c-193">DestroyICeeFileGen (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-193">DestroyICeeFileGen Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md)  
 <span data-ttu-id="9860c-194">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-194">Deprecated.</span></span> <span data-ttu-id="9860c-195">Destruye una [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="9860c-195">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="9860c-196">Función FExecuteInAppDomainCallback</span><span class="sxs-lookup"><span data-stu-id="9860c-196">FExecuteInAppDomainCallback Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/fexecuteinappdomaincallback-function-pointer.md)  
 <span data-ttu-id="9860c-197">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-197">Deprecated.</span></span> <span data-ttu-id="9860c-198">Señala a una función que llama a CLR para ejecutar código administrado.</span><span class="sxs-lookup"><span data-stu-id="9860c-198">Points to a function that the CLR calls to execute managed code.</span></span>  
  
 [<span data-ttu-id="9860c-199">Puntero a la función FLockClrVersionCallback</span><span class="sxs-lookup"><span data-stu-id="9860c-199">FLockClrVersionCallback Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md)  
 <span data-ttu-id="9860c-200">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-200">Deprecated.</span></span> <span data-ttu-id="9860c-201">Señala a una función que CLR llama para notificar al host que la inicialización se ha iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="9860c-201">Points to a function that the CLR calls to notify the host that initialization has either started or completed.</span></span>  
  
 [<span data-ttu-id="9860c-202">GetCLRIdentityManager (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-202">GetCLRIdentityManager Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getclridentitymanager-function.md)  
 <span data-ttu-id="9860c-203">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-203">Deprecated.</span></span> <span data-ttu-id="9860c-204">Obtiene un puntero a una interfaz que permite a CLR administrar identidades.</span><span class="sxs-lookup"><span data-stu-id="9860c-204">Gets a pointer to an interface that allows the CLR to manage identities.</span></span>  
  
 [<span data-ttu-id="9860c-205">LoadLibraryShim (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-205">LoadLibraryShim Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md)  
 <span data-ttu-id="9860c-206">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-206">Deprecated.</span></span> <span data-ttu-id="9860c-207">Carga la versión especificada de una DLL de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9860c-207">Loads a specified version of a .NET Framework DLL.</span></span>  
  
 [<span data-ttu-id="9860c-208">LoadStringRC (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-208">LoadStringRC Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
 <span data-ttu-id="9860c-209">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-209">Deprecated.</span></span> <span data-ttu-id="9860c-210">Convierte un valor HRESULT en un mensaje de error mediante el uso de la referencia cultural predeterminada del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="9860c-210">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 [<span data-ttu-id="9860c-211">LoadStringRCEx (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-211">LoadStringRCEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
 <span data-ttu-id="9860c-212">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-212">Deprecated.</span></span> <span data-ttu-id="9860c-213">Convierte un valor HRESULT a un mensaje de error adecuado para la referencia cultural especificada.</span><span class="sxs-lookup"><span data-stu-id="9860c-213">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 [<span data-ttu-id="9860c-214">La función Lpoverlapped_completion_routine</span><span class="sxs-lookup"><span data-stu-id="9860c-214">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/lpoverlapped-completion-routine-function-pointer.md)  
 <span data-ttu-id="9860c-215">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-215">Deprecated.</span></span> <span data-ttu-id="9860c-216">Señala a una función que notifica al host cuándo una superposición (es decir, asincrónica) ha completado la E/S en un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9860c-216">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 [<span data-ttu-id="9860c-217">La función Lpthread_start_routine</span><span class="sxs-lookup"><span data-stu-id="9860c-217">LPTHREAD_START_ROUTINE Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/lpthread-start-routine-function-pointer.md)  
 <span data-ttu-id="9860c-218">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-218">Deprecated.</span></span> <span data-ttu-id="9860c-219">Señala a una función que notifica al host que ha empezado a ejecutar un subproceso.</span><span class="sxs-lookup"><span data-stu-id="9860c-219">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 [<span data-ttu-id="9860c-220">RunDll32ShimW (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-220">RunDll32ShimW Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/rundll32shimw-function.md)  
 <span data-ttu-id="9860c-221">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-221">Deprecated.</span></span> <span data-ttu-id="9860c-222">Ejecuta el comando especificado.</span><span class="sxs-lookup"><span data-stu-id="9860c-222">Executes the specified command.</span></span>  
  
 [<span data-ttu-id="9860c-223">Puntero a función WAITORTIMERCALLBACK</span><span class="sxs-lookup"><span data-stu-id="9860c-223">WAITORTIMERCALLBACK Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/waitortimercallback-function-pointer.md)  
 <span data-ttu-id="9860c-224">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9860c-224">Deprecated.</span></span> <span data-ttu-id="9860c-225">Señala a una función que notifica al host que un identificador de espera se ha señalado o agotó el tiempo.</span><span class="sxs-lookup"><span data-stu-id="9860c-225">Points to a function that notifies the host that a wait handle has either been signaled or timed out.</span></span>  
  
## <a name="infrastructure-functions"></a><span data-ttu-id="9860c-226">Funciones de infraestructura</span><span class="sxs-lookup"><span data-stu-id="9860c-226">Infrastructure functions</span></span>  
 <span data-ttu-id="9860c-227">Las funciones de esta sección son para uso sólo .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9860c-227">The functions in this section are for use by the .NET Framework only.</span></span>  
  
 [<span data-ttu-id="9860c-228">_CorDllMain (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-228">_CorDllMain Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)  
 <span data-ttu-id="9860c-229">Inicializa el CLR, busca el punto de entrada administrado en el encabezado CLR del ensamblado de la DLL y comienza la ejecución.</span><span class="sxs-lookup"><span data-stu-id="9860c-229">Initializes the CLR, locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="9860c-230">_CorExeMain (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-230">_CorExeMain Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)  
 <span data-ttu-id="9860c-231">Inicializa el CLR, busca el punto de entrada administrado en el encabezado CLR del ensamblado ejecutable y comienza la ejecución.</span><span class="sxs-lookup"><span data-stu-id="9860c-231">Initializes the CLR, locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="9860c-232">_CorExeMain2 (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-232">_CorExeMain2 Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corexemain2-function.md)  
 <span data-ttu-id="9860c-233">Ejecuta el punto de entrada en el código asignado a la memoria especificado.</span><span class="sxs-lookup"><span data-stu-id="9860c-233">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="9860c-234">Esta función se invoca por el cargador del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="9860c-234">This function is called by the operating system loader.</span></span>  
  
 [<span data-ttu-id="9860c-235">_CorImageUnloading (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-235">_CorImageUnloading Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md)  
 <span data-ttu-id="9860c-236">Notifica al cargador cuándo se descargan imágenes del módulo administrado.</span><span class="sxs-lookup"><span data-stu-id="9860c-236">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 [<span data-ttu-id="9860c-237">_CorValidateImage (función)</span><span class="sxs-lookup"><span data-stu-id="9860c-237">_CorValidateImage Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)  
 <span data-ttu-id="9860c-238">Valida las imágenes del módulo administrado y notifica el cargador del sistema operativo después de que se han cargado.</span><span class="sxs-lookup"><span data-stu-id="9860c-238">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9860c-239">Vea también</span><span class="sxs-lookup"><span data-stu-id="9860c-239">See Also</span></span>  
 [<span data-ttu-id="9860c-240">.NET framework 4 aloja funciones estáticas globales</span><span class="sxs-lookup"><span data-stu-id="9860c-240">.NET Framework 4 Hosting Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/net-framework-4-hosting-global-static-functions.md) 
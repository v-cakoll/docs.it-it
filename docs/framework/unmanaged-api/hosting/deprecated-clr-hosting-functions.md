---
title: Funzioni di hosting CLR deprecate
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
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="deprecated-clr-hosting-functions"></a><span data-ttu-id="c382a-102">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="c382a-102">Deprecated CLR Hosting Functions</span></span>
<span data-ttu-id="c382a-103">In questa sezione vengono descritte le funzioni statiche globali non gestite utilizzate versioni precedenti dell'API di hosting.</span><span class="sxs-lookup"><span data-stu-id="c382a-103">This section describes the unmanaged global static functions that earlier versions of the hosting API used.</span></span>  
  
 <span data-ttu-id="c382a-104">Fatta eccezione per le funzioni di infrastruttura (`_Cor*` funzioni), che vengono utilizzati solo da .NET Framework, queste funzioni sono state deprecate nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c382a-104">With the exception of the infrastructure functions (`_Cor*` functions), which are used only by the .NET Framework, these functions have been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="activation-functions"></a><span data-ttu-id="c382a-105">Funzioni di attivazione</span><span class="sxs-lookup"><span data-stu-id="c382a-105">Activation functions</span></span>  
 [<span data-ttu-id="c382a-106">ClrCreateManagedInstance (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-106">ClrCreateManagedInstance Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/clrcreatemanagedinstance-function.md)  
 <span data-ttu-id="c382a-107">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-107">Deprecated.</span></span> <span data-ttu-id="c382a-108">Crea un'istanza del tipo gestito specificato.</span><span class="sxs-lookup"><span data-stu-id="c382a-108">Creates an instance of the specified managed type.</span></span>  
  
 [<span data-ttu-id="c382a-109">CoInitializeCor (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-109">CoInitializeCor Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializecor-function.md)  
 <span data-ttu-id="c382a-110">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="c382a-110">Obsolete.</span></span> <span data-ttu-id="c382a-111">Per inizializzare common language runtime (CLR), utilizzare [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="c382a-111">To initialize the common language runtime (CLR), use either [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span>  
  
 [<span data-ttu-id="c382a-112">CoInitializeEE (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-112">CoInitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)  
 <span data-ttu-id="c382a-113">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-113">Deprecated.</span></span> <span data-ttu-id="c382a-114">Assicura che il motore di esecuzione di CLR viene caricato in un processo.</span><span class="sxs-lookup"><span data-stu-id="c382a-114">Ensures that the CLR execution engine is loaded into a process.</span></span> <span data-ttu-id="c382a-115">Utilizzare il [ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="c382a-115">Use the [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method instead.</span></span>  
  
 [<span data-ttu-id="c382a-116">CorBindToCurrentRuntime (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-116">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 <span data-ttu-id="c382a-117">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-117">Deprecated.</span></span> <span data-ttu-id="c382a-118">Carica common language runtime (CLR) in un processo con informazioni sulla versione memorizzate in un file XML.</span><span class="sxs-lookup"><span data-stu-id="c382a-118">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span>  
  
 [<span data-ttu-id="c382a-119">CorBindToRuntime (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-119">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 <span data-ttu-id="c382a-120">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-120">Deprecated.</span></span> <span data-ttu-id="c382a-121">Consente agli caricare CLR in un processo host non gestiti.</span><span class="sxs-lookup"><span data-stu-id="c382a-121">Enables unmanaged hosts to load the CLR into a process.</span></span>  
  
 [<span data-ttu-id="c382a-122">CorBindToRuntimeByCfg (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-122">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 <span data-ttu-id="c382a-123">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-123">Deprecated.</span></span> <span data-ttu-id="c382a-124">Carica CLR in un processo con informazioni sulla versione che viene letto da un file XML.</span><span class="sxs-lookup"><span data-stu-id="c382a-124">Loads the CLR into a process by using version information that is read from an XML file.</span></span>  
  
 [<span data-ttu-id="c382a-125">CorBindToRuntimeEx (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-125">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 <span data-ttu-id="c382a-126">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-126">Deprecated.</span></span> <span data-ttu-id="c382a-127">Consente agli host non gestiti di caricamento di CLR in un processo e consente di impostare flag per specificare il comportamento di CLR.</span><span class="sxs-lookup"><span data-stu-id="c382a-127">Enables unmanaged hosts to load the CLR into a process, and allows you to set flags to specify the behavior of the CLR.</span></span>  
  
 [<span data-ttu-id="c382a-128">CorBindToRuntimeHost (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 <span data-ttu-id="c382a-129">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-129">Deprecated.</span></span> <span data-ttu-id="c382a-130">Consente agli host di caricare una versione specifica di CLR in un processo.</span><span class="sxs-lookup"><span data-stu-id="c382a-130">Enables hosts to load a specified version of the CLR into a process.</span></span>  
  
 [<span data-ttu-id="c382a-131">GetCORRequiredVersion (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-131">GetCORRequiredVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getcorrequiredversion-function.md)  
 <span data-ttu-id="c382a-132">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-132">Deprecated.</span></span> <span data-ttu-id="c382a-133">Ottiene il numero di versione CLR richiesto.</span><span class="sxs-lookup"><span data-stu-id="c382a-133">Gets the required CLR version number.</span></span>  
  
 [<span data-ttu-id="c382a-134">GetCORSystemDirectory (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-134">GetCORSystemDirectory Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md)  
 <span data-ttu-id="c382a-135">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-135">Deprecated.</span></span> <span data-ttu-id="c382a-136">Restituisce la directory di installazione di CLR caricati nel processo.</span><span class="sxs-lookup"><span data-stu-id="c382a-136">Returns the installation directory of the CLR that is loaded into the process.</span></span>  
  
 [<span data-ttu-id="c382a-137">GetRealProcAddress (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-137">GetRealProcAddress Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md)  
 <span data-ttu-id="c382a-138">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-138">Deprecated.</span></span> <span data-ttu-id="c382a-139">Ottiene l'indirizzo della funzione specificata esportata dall'ultima versione installata di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="c382a-139">Gets the address of the specified function that is exported from the latest installed version of the CLR.</span></span>  
  
 [<span data-ttu-id="c382a-140">GetRequestedRuntimeInfo (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-140">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 <span data-ttu-id="c382a-141">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-141">Deprecated.</span></span> <span data-ttu-id="c382a-142">Ottiene informazioni di versione e la directory CLR richiesto da un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c382a-142">Gets version and directory information about the CLR requested by an application.</span></span>  
  
## <a name="clr-version-functions"></a><span data-ttu-id="c382a-143">Funzioni di versione CLR</span><span class="sxs-lookup"><span data-stu-id="c382a-143">CLR version functions</span></span>  
 <span data-ttu-id="c382a-144">Le funzioni in questa sezione restituiscono una versione CLR. CLR non attivano.</span><span class="sxs-lookup"><span data-stu-id="c382a-144">The functions in this section return a CLR version; they do not activate the CLR.</span></span>  
  
 [<span data-ttu-id="c382a-145">GetCORVersion (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-145">GetCORVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getcorversion-function.md)  
 <span data-ttu-id="c382a-146">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-146">Deprecated.</span></span> <span data-ttu-id="c382a-147">Restituisce il numero di versione di CLR è in esecuzione nel processo corrente.</span><span class="sxs-lookup"><span data-stu-id="c382a-147">Returns the version number of the CLR that is running in the current process.</span></span>  
  
 [<span data-ttu-id="c382a-148">GetFileVersion (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-148">GetFileVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md)  
 <span data-ttu-id="c382a-149">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-149">Deprecated.</span></span> <span data-ttu-id="c382a-150">Ottiene le informazioni sulla versione CLR del file specificato, utilizzando il buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="c382a-150">Gets the CLR version information of the specified file, using the specified buffer.</span></span>  
  
 [<span data-ttu-id="c382a-151">GetRequestedRuntimeVersion (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-151">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 <span data-ttu-id="c382a-152">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-152">Deprecated.</span></span> <span data-ttu-id="c382a-153">Ottiene il numero di versione di CLR richiesto dall'applicazione specificata.</span><span class="sxs-lookup"><span data-stu-id="c382a-153">Gets the version number of the CLR requested by the specified application.</span></span> <span data-ttu-id="c382a-154">Se tale versione non è installata, ottiene la versione più recente installata prima la versione richiesta.</span><span class="sxs-lookup"><span data-stu-id="c382a-154">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 [<span data-ttu-id="c382a-155">GetRequestedRuntimeVersionForCLSID (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-155">GetRequestedRuntimeVersionForCLSID Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversionforclsid-function.md)  
 <span data-ttu-id="c382a-156">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-156">Deprecated.</span></span> <span data-ttu-id="c382a-157">Ottiene le informazioni sulla versione CLR appropriati per la classe con il CLSID specificato.</span><span class="sxs-lookup"><span data-stu-id="c382a-157">Gets the appropriate CLR version information for the class with the specified CLSID.</span></span>  
  
 [<span data-ttu-id="c382a-158">GetVersionFromProcess (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-158">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)  
 <span data-ttu-id="c382a-159">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-159">Deprecated.</span></span> <span data-ttu-id="c382a-160">Ottiene il numero di versione di Common Language Runtime che è associato l'handle del processo specificato.</span><span class="sxs-lookup"><span data-stu-id="c382a-160">Gets the version number of the CLR that is associated with the specified process handle.</span></span>  
  
 [<span data-ttu-id="c382a-161">LockClrVersion (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-161">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)  
 <span data-ttu-id="c382a-162">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-162">Deprecated.</span></span> <span data-ttu-id="c382a-163">Consente all'host determinare quale versione di CLR verrà utilizzata all'interno del processo prima di inizializzare in modo esplicito il CLR.</span><span class="sxs-lookup"><span data-stu-id="c382a-163">Allows the host to determine which version of the CLR will be used within the process before explicitly initializing the CLR.</span></span>  
  
## <a name="hosting-functions"></a><span data-ttu-id="c382a-164">Funzioni di hosting</span><span class="sxs-lookup"><span data-stu-id="c382a-164">Hosting functions</span></span>  
 [<span data-ttu-id="c382a-165">CallFunctionShim (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-165">CallFunctionShim Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/callfunctionshim-function.md)  
 <span data-ttu-id="c382a-166">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-166">Deprecated.</span></span> <span data-ttu-id="c382a-167">Effettua una chiamata alla funzione che contiene i parametri e il nome specificato nella libreria specificata.</span><span class="sxs-lookup"><span data-stu-id="c382a-167">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 [<span data-ttu-id="c382a-168">CoEEShutDownCOM (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-168">CoEEShutDownCOM Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coeeshutdowncom-function.md)  
 <span data-ttu-id="c382a-169">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-169">Deprecated.</span></span> <span data-ttu-id="c382a-170">Scarica un assembly COM dal processo.</span><span class="sxs-lookup"><span data-stu-id="c382a-170">Unloads a COM assembly from the process.</span></span>  
  
 [<span data-ttu-id="c382a-171">CorExitProcess (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-171">CorExitProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)  
 <span data-ttu-id="c382a-172">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-172">Deprecated.</span></span> <span data-ttu-id="c382a-173">Arresta il processo corrente non gestito.</span><span class="sxs-lookup"><span data-stu-id="c382a-173">Shuts down the current unmanaged process.</span></span>  
  
 [<span data-ttu-id="c382a-174">CorLaunchApplication (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-174">CorLaunchApplication Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corlaunchapplication-function.md)  
 <span data-ttu-id="c382a-175">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-175">Deprecated.</span></span> <span data-ttu-id="c382a-176">Avvia l'applicazione in corrispondenza del percorso di rete specificato, utilizzando i manifesti specificati e altri dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c382a-176">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 [<span data-ttu-id="c382a-177">CorMarkThreadInThreadPool (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-177">CorMarkThreadInThreadPool Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/cormarkthreadinthreadpool-function.md)  
 <span data-ttu-id="c382a-178">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-178">Deprecated.</span></span> <span data-ttu-id="c382a-179">Contrassegna il thread di pool di thread attualmente in esecuzione per l'esecuzione di codice gestito.</span><span class="sxs-lookup"><span data-stu-id="c382a-179">Marks the currently executing thread-pool thread for the execution of managed code.</span></span> <span data-ttu-id="c382a-180">A partire da .NET Framework versione 2.0, questa funzione non ha effetto.</span><span class="sxs-lookup"><span data-stu-id="c382a-180">Starting with the .NET Framework version 2.0, this function has no effect.</span></span> <span data-ttu-id="c382a-181">Non è obbligatorio e può essere rimossa dal codice.</span><span class="sxs-lookup"><span data-stu-id="c382a-181">It is not required, and can be removed from your code.</span></span>  
  
 [<span data-ttu-id="c382a-182">CoUninitializeCor (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-182">CoUninitializeCor Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)  
 <span data-ttu-id="c382a-183">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="c382a-183">Obsolete.</span></span> <span data-ttu-id="c382a-184">CLR non può essere scaricato da un processo.</span><span class="sxs-lookup"><span data-stu-id="c382a-184">The CLR cannot be unloaded from a process.</span></span>  
  
 [<span data-ttu-id="c382a-185">CoUninitializeEE (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-185">CoUninitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md)  
 <span data-ttu-id="c382a-186">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="c382a-186">Obsolete.</span></span>  
  
 [<span data-ttu-id="c382a-187">CreateDebuggingInterfaceFromVersion (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-187">CreateDebuggingInterfaceFromVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md)  
 <span data-ttu-id="c382a-188">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-188">Deprecated.</span></span> <span data-ttu-id="c382a-189">Crea un [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) oggetto in base alle informazioni di versione specificata.</span><span class="sxs-lookup"><span data-stu-id="c382a-189">Creates an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 [<span data-ttu-id="c382a-190">CreateICeeFileGen (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-190">CreateICeeFileGen Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md)  
 <span data-ttu-id="c382a-191">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-191">Deprecated.</span></span> <span data-ttu-id="c382a-192">Crea un [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="c382a-192">Creates an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="c382a-193">DestroyICeeFileGen (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-193">DestroyICeeFileGen Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md)  
 <span data-ttu-id="c382a-194">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-194">Deprecated.</span></span> <span data-ttu-id="c382a-195">Elimina definitivamente un [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="c382a-195">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="c382a-196">Puntatore alla funzione FExecuteInAppDomainCallback</span><span class="sxs-lookup"><span data-stu-id="c382a-196">FExecuteInAppDomainCallback Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/fexecuteinappdomaincallback-function-pointer.md)  
 <span data-ttu-id="c382a-197">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-197">Deprecated.</span></span> <span data-ttu-id="c382a-198">Punta a una funzione chiamata da CLR per eseguire codice gestito.</span><span class="sxs-lookup"><span data-stu-id="c382a-198">Points to a function that the CLR calls to execute managed code.</span></span>  
  
 [<span data-ttu-id="c382a-199">Puntatore alla funzione FLockClrVersionCallback</span><span class="sxs-lookup"><span data-stu-id="c382a-199">FLockClrVersionCallback Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md)  
 <span data-ttu-id="c382a-200">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-200">Deprecated.</span></span> <span data-ttu-id="c382a-201">Punta a una funzione chiamata da CLR per notificare all'host che l'inizializzazione è avviato o completato.</span><span class="sxs-lookup"><span data-stu-id="c382a-201">Points to a function that the CLR calls to notify the host that initialization has either started or completed.</span></span>  
  
 [<span data-ttu-id="c382a-202">GetCLRIdentityManager (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-202">GetCLRIdentityManager Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getclridentitymanager-function.md)  
 <span data-ttu-id="c382a-203">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-203">Deprecated.</span></span> <span data-ttu-id="c382a-204">Ottiene un puntatore a un'interfaccia che consente a CLR gestire le identità.</span><span class="sxs-lookup"><span data-stu-id="c382a-204">Gets a pointer to an interface that allows the CLR to manage identities.</span></span>  
  
 [<span data-ttu-id="c382a-205">LoadLibraryShim (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-205">LoadLibraryShim Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md)  
 <span data-ttu-id="c382a-206">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-206">Deprecated.</span></span> <span data-ttu-id="c382a-207">Carica una versione specifica di una DLL di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c382a-207">Loads a specified version of a .NET Framework DLL.</span></span>  
  
 [<span data-ttu-id="c382a-208">LoadStringRC (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-208">LoadStringRC Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
 <span data-ttu-id="c382a-209">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-209">Deprecated.</span></span> <span data-ttu-id="c382a-210">Converte un valore HRESULT in un messaggio di errore utilizzando le impostazioni cultura predefinite del thread corrente.</span><span class="sxs-lookup"><span data-stu-id="c382a-210">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 [<span data-ttu-id="c382a-211">LoadStringRCEx (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-211">LoadStringRCEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
 <span data-ttu-id="c382a-212">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-212">Deprecated.</span></span> <span data-ttu-id="c382a-213">Converte un valore HRESULT a un messaggio di errore appropriato per le impostazioni cultura specificate.</span><span class="sxs-lookup"><span data-stu-id="c382a-213">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 [<span data-ttu-id="c382a-214">Alla funzione Lpoverlapped_completion_routine</span><span class="sxs-lookup"><span data-stu-id="c382a-214">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/lpoverlapped-completion-routine-function-pointer.md)  
 <span data-ttu-id="c382a-215">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-215">Deprecated.</span></span> <span data-ttu-id="c382a-216">Punta a una funzione che notifica all'host quando un sovrapposte (vale a dire asincrona) i/o in un dispositivo è stata completata.</span><span class="sxs-lookup"><span data-stu-id="c382a-216">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 [<span data-ttu-id="c382a-217">Alla funzione Lpthread_start_routine</span><span class="sxs-lookup"><span data-stu-id="c382a-217">LPTHREAD_START_ROUTINE Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/lpthread-start-routine-function-pointer.md)  
 <span data-ttu-id="c382a-218">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-218">Deprecated.</span></span> <span data-ttu-id="c382a-219">Punta a una funzione che notifica all'host che un thread è stata avviata l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c382a-219">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 [<span data-ttu-id="c382a-220">RunDll32ShimW (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-220">RunDll32ShimW Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/rundll32shimw-function.md)  
 <span data-ttu-id="c382a-221">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-221">Deprecated.</span></span> <span data-ttu-id="c382a-222">Esegue il comando specificato.</span><span class="sxs-lookup"><span data-stu-id="c382a-222">Executes the specified command.</span></span>  
  
 [<span data-ttu-id="c382a-223">Puntatore alla funzione WAITORTIMERCALLBACK</span><span class="sxs-lookup"><span data-stu-id="c382a-223">WAITORTIMERCALLBACK Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/waitortimercallback-function-pointer.md)  
 <span data-ttu-id="c382a-224">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c382a-224">Deprecated.</span></span> <span data-ttu-id="c382a-225">Punta a una funzione che notifica all'host che un handle di attesa è stato segnalato oppure timeout.</span><span class="sxs-lookup"><span data-stu-id="c382a-225">Points to a function that notifies the host that a wait handle has either been signaled or timed out.</span></span>  
  
## <a name="infrastructure-functions"></a><span data-ttu-id="c382a-226">Funzioni di infrastruttura</span><span class="sxs-lookup"><span data-stu-id="c382a-226">Infrastructure functions</span></span>  
 <span data-ttu-id="c382a-227">Le funzioni in questa sezione possono essere utilizzati da solo .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c382a-227">The functions in this section are for use by the .NET Framework only.</span></span>  
  
 [<span data-ttu-id="c382a-228">CorDllMain (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-228">_CorDllMain Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)  
 <span data-ttu-id="c382a-229">Inizializza il CLR, individua il punto di ingresso gestito nell'intestazione CLR dell'assembly DLL e inizia l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c382a-229">Initializes the CLR, locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="c382a-230">CorExeMain (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-230">_CorExeMain Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)  
 <span data-ttu-id="c382a-231">Inizializza il CLR, individua il punto di ingresso gestito nell'intestazione CLR dell'assembly eseguibile e inizia l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c382a-231">Initializes the CLR, locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="c382a-232">CorExeMain2 (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-232">_CorExeMain2 Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corexemain2-function.md)  
 <span data-ttu-id="c382a-233">Esegue il punto di ingresso nel codice mappato alla memoria specificato.</span><span class="sxs-lookup"><span data-stu-id="c382a-233">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="c382a-234">Questa funzione viene chiamata dal caricatore del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="c382a-234">This function is called by the operating system loader.</span></span>  
  
 [<span data-ttu-id="c382a-235">CorImageUnloading (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-235">_CorImageUnloading Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md)  
 <span data-ttu-id="c382a-236">Notifica al caricatore quando vengono scaricate le immagini dei moduli gestiti.</span><span class="sxs-lookup"><span data-stu-id="c382a-236">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 [<span data-ttu-id="c382a-237">CorValidateImage (funzione)</span><span class="sxs-lookup"><span data-stu-id="c382a-237">_CorValidateImage Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)  
 <span data-ttu-id="c382a-238">Convalida delle immagini dei moduli gestiti e notifica al caricatore del sistema operativo dopo che sono stati caricati.</span><span class="sxs-lookup"><span data-stu-id="c382a-238">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c382a-239">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c382a-239">See Also</span></span>  
 [<span data-ttu-id="c382a-240">.NET framework 4 funzioni globali di Hosting statiche</span><span class="sxs-lookup"><span data-stu-id="c382a-240">.NET Framework 4 Hosting Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/net-framework-4-hosting-global-static-functions.md) 

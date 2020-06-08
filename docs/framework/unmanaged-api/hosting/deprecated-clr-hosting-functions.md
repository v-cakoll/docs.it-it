---
title: Funzioni di hosting CLR deprecate
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
ms.openlocfilehash: 083d0ff285abb4a99ad05c791bc504ff7f282c6a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504368"
---
# <a name="deprecated-clr-hosting-functions"></a><span data-ttu-id="2e926-102">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="2e926-102">Deprecated CLR Hosting Functions</span></span>
<span data-ttu-id="2e926-103">Questa sezione descrive le funzioni statiche globali non gestite usate dalle versioni precedenti dell'API di hosting.</span><span class="sxs-lookup"><span data-stu-id="2e926-103">This section describes the unmanaged global static functions that earlier versions of the hosting API used.</span></span>  
  
 <span data-ttu-id="2e926-104">Fatta eccezione per le funzioni di infrastruttura ( `_Cor*` funzioni), che vengono utilizzate solo dal .NET Framework, queste funzioni sono state deprecate nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="2e926-104">With the exception of the infrastructure functions (`_Cor*` functions), which are used only by the .NET Framework, these functions have been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="activation-functions"></a><span data-ttu-id="2e926-105">Funzioni di attivazione</span><span class="sxs-lookup"><span data-stu-id="2e926-105">Activation functions</span></span>  
 [<span data-ttu-id="2e926-106">Funzione ClrCreateManagedInstance</span><span class="sxs-lookup"><span data-stu-id="2e926-106">ClrCreateManagedInstance Function</span></span>](clrcreatemanagedinstance-function.md)  
 <span data-ttu-id="2e926-107">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-107">Deprecated.</span></span> <span data-ttu-id="2e926-108">Crea un'istanza del tipo gestito specificato.</span><span class="sxs-lookup"><span data-stu-id="2e926-108">Creates an instance of the specified managed type.</span></span>  
  
 [<span data-ttu-id="2e926-109">Funzione CoInitializeCor</span><span class="sxs-lookup"><span data-stu-id="2e926-109">CoInitializeCor Function</span></span>](coinitializecor-function.md)  
 <span data-ttu-id="2e926-110">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="2e926-110">Obsolete.</span></span> <span data-ttu-id="2e926-111">Per inizializzare il Common Language Runtime (CLR), utilizzare [CorBindToRuntimeEx](corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="2e926-111">To initialize the common language runtime (CLR), use either [CorBindToRuntimeEx](corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).</span></span>  
  
 [<span data-ttu-id="2e926-112">Funzione CoInitializeEE</span><span class="sxs-lookup"><span data-stu-id="2e926-112">CoInitializeEE Function</span></span>](coinitializeee-function.md)  
 <span data-ttu-id="2e926-113">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-113">Deprecated.</span></span> <span data-ttu-id="2e926-114">Garantisce che il motore di esecuzione CLR venga caricato in un processo.</span><span class="sxs-lookup"><span data-stu-id="2e926-114">Ensures that the CLR execution engine is loaded into a process.</span></span> <span data-ttu-id="2e926-115">Usare invece il metodo [ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2e926-115">Use the [ICLRRuntimeHost::Start](iclrruntimehost-start-method.md) method instead.</span></span>  
  
 [<span data-ttu-id="2e926-116">Funzione CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="2e926-116">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)  
 <span data-ttu-id="2e926-117">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-117">Deprecated.</span></span> <span data-ttu-id="2e926-118">Carica il Common Language Runtime (CLR) in un processo utilizzando le informazioni sulla versione archiviate in un file XML.</span><span class="sxs-lookup"><span data-stu-id="2e926-118">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span>  
  
 [<span data-ttu-id="2e926-119">Funzione CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="2e926-119">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)  
 <span data-ttu-id="2e926-120">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-120">Deprecated.</span></span> <span data-ttu-id="2e926-121">Consente agli host non gestiti di caricare il CLR in un processo.</span><span class="sxs-lookup"><span data-stu-id="2e926-121">Enables unmanaged hosts to load the CLR into a process.</span></span>  
  
 [<span data-ttu-id="2e926-122">Funzione CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="2e926-122">CorBindToRuntimeByCfg Function</span></span>](corbindtoruntimebycfg-function.md)  
 <span data-ttu-id="2e926-123">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-123">Deprecated.</span></span> <span data-ttu-id="2e926-124">Carica CLR in un processo utilizzando le informazioni sulla versione lette da un file XML.</span><span class="sxs-lookup"><span data-stu-id="2e926-124">Loads the CLR into a process by using version information that is read from an XML file.</span></span>  
  
 [<span data-ttu-id="2e926-125">Funzione CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="2e926-125">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)  
 <span data-ttu-id="2e926-126">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-126">Deprecated.</span></span> <span data-ttu-id="2e926-127">Consente agli host non gestiti di caricare il CLR in un processo e consente di impostare i flag per specificare il comportamento di CLR.</span><span class="sxs-lookup"><span data-stu-id="2e926-127">Enables unmanaged hosts to load the CLR into a process, and allows you to set flags to specify the behavior of the CLR.</span></span>  
  
 [<span data-ttu-id="2e926-128">Funzione CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="2e926-128">CorBindToRuntimeHost Function</span></span>](corbindtoruntimehost-function.md)  
 <span data-ttu-id="2e926-129">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-129">Deprecated.</span></span> <span data-ttu-id="2e926-130">Consente agli host di caricare una versione specificata di CLR in un processo.</span><span class="sxs-lookup"><span data-stu-id="2e926-130">Enables hosts to load a specified version of the CLR into a process.</span></span>  
  
 [<span data-ttu-id="2e926-131">Funzione GetCORRequiredVersion</span><span class="sxs-lookup"><span data-stu-id="2e926-131">GetCORRequiredVersion Function</span></span>](getcorrequiredversion-function.md)  
 <span data-ttu-id="2e926-132">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-132">Deprecated.</span></span> <span data-ttu-id="2e926-133">Ottiene il numero della versione CLR richiesta.</span><span class="sxs-lookup"><span data-stu-id="2e926-133">Gets the required CLR version number.</span></span>  
  
 [<span data-ttu-id="2e926-134">Funzione GetCORSystemDirectory</span><span class="sxs-lookup"><span data-stu-id="2e926-134">GetCORSystemDirectory Function</span></span>](getcorsystemdirectory-function.md)  
 <span data-ttu-id="2e926-135">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-135">Deprecated.</span></span> <span data-ttu-id="2e926-136">Restituisce la directory di installazione di CLR caricata nel processo.</span><span class="sxs-lookup"><span data-stu-id="2e926-136">Returns the installation directory of the CLR that is loaded into the process.</span></span>  
  
 [<span data-ttu-id="2e926-137">Funzione GetRealProcAddress</span><span class="sxs-lookup"><span data-stu-id="2e926-137">GetRealProcAddress Function</span></span>](getrealprocaddress-function.md)  
 <span data-ttu-id="2e926-138">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-138">Deprecated.</span></span> <span data-ttu-id="2e926-139">Ottiene l'indirizzo della funzione specificata esportata dall'ultima versione installata di CLR.</span><span class="sxs-lookup"><span data-stu-id="2e926-139">Gets the address of the specified function that is exported from the latest installed version of the CLR.</span></span>  
  
 [<span data-ttu-id="2e926-140">Funzione GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="2e926-140">GetRequestedRuntimeInfo Function</span></span>](getrequestedruntimeinfo-function.md)  
 <span data-ttu-id="2e926-141">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-141">Deprecated.</span></span> <span data-ttu-id="2e926-142">Ottiene le informazioni sulla versione e sulla directory relative a CLR richieste da un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2e926-142">Gets version and directory information about the CLR requested by an application.</span></span>  
  
## <a name="clr-version-functions"></a><span data-ttu-id="2e926-143">Funzioni della versione CLR</span><span class="sxs-lookup"><span data-stu-id="2e926-143">CLR version functions</span></span>  
 <span data-ttu-id="2e926-144">Le funzioni in questa sezione restituiscono una versione CLR; non attivano CLR.</span><span class="sxs-lookup"><span data-stu-id="2e926-144">The functions in this section return a CLR version; they do not activate the CLR.</span></span>  
  
 [<span data-ttu-id="2e926-145">Funzione GetCORVersion</span><span class="sxs-lookup"><span data-stu-id="2e926-145">GetCORVersion Function</span></span>](getcorversion-function.md)  
 <span data-ttu-id="2e926-146">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-146">Deprecated.</span></span> <span data-ttu-id="2e926-147">Restituisce il numero di versione di CLR in esecuzione nel processo corrente.</span><span class="sxs-lookup"><span data-stu-id="2e926-147">Returns the version number of the CLR that is running in the current process.</span></span>  
  
 [<span data-ttu-id="2e926-148">Funzione GetFileVersion</span><span class="sxs-lookup"><span data-stu-id="2e926-148">GetFileVersion Function</span></span>](getfileversion-function.md)  
 <span data-ttu-id="2e926-149">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-149">Deprecated.</span></span> <span data-ttu-id="2e926-150">Ottiene le informazioni sulla versione CLR del file specificato, utilizzando il buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="2e926-150">Gets the CLR version information of the specified file, using the specified buffer.</span></span>  
  
 [<span data-ttu-id="2e926-151">Funzione GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="2e926-151">GetRequestedRuntimeVersion Function</span></span>](getrequestedruntimeversion-function.md)  
 <span data-ttu-id="2e926-152">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-152">Deprecated.</span></span> <span data-ttu-id="2e926-153">Ottiene il numero di versione di CLR richiesto dall'applicazione specificata.</span><span class="sxs-lookup"><span data-stu-id="2e926-153">Gets the version number of the CLR requested by the specified application.</span></span> <span data-ttu-id="2e926-154">Se tale versione non è installata, ottiene la versione più recente installata prima della versione richiesta.</span><span class="sxs-lookup"><span data-stu-id="2e926-154">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 [<span data-ttu-id="2e926-155">Funzione GetRequestedRuntimeVersionForCLSID</span><span class="sxs-lookup"><span data-stu-id="2e926-155">GetRequestedRuntimeVersionForCLSID Function</span></span>](getrequestedruntimeversionforclsid-function.md)  
 <span data-ttu-id="2e926-156">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-156">Deprecated.</span></span> <span data-ttu-id="2e926-157">Ottiene le informazioni sulla versione CLR appropriate per la classe con il CLSID specificato.</span><span class="sxs-lookup"><span data-stu-id="2e926-157">Gets the appropriate CLR version information for the class with the specified CLSID.</span></span>  
  
 [<span data-ttu-id="2e926-158">Funzione GetVersionFromProcess</span><span class="sxs-lookup"><span data-stu-id="2e926-158">GetVersionFromProcess Function</span></span>](getversionfromprocess-function.md)  
 <span data-ttu-id="2e926-159">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-159">Deprecated.</span></span> <span data-ttu-id="2e926-160">Ottiene il numero di versione di CLR associato all'handle di processo specificato.</span><span class="sxs-lookup"><span data-stu-id="2e926-160">Gets the version number of the CLR that is associated with the specified process handle.</span></span>  
  
 [<span data-ttu-id="2e926-161">Funzione LockClrVersion</span><span class="sxs-lookup"><span data-stu-id="2e926-161">LockClrVersion Function</span></span>](lockclrversion-function.md)  
 <span data-ttu-id="2e926-162">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-162">Deprecated.</span></span> <span data-ttu-id="2e926-163">Consente all'host di determinare quale versione di CLR verrà utilizzata all'interno del processo prima di inizializzare in modo esplicito CLR.</span><span class="sxs-lookup"><span data-stu-id="2e926-163">Allows the host to determine which version of the CLR will be used within the process before explicitly initializing the CLR.</span></span>  
  
## <a name="hosting-functions"></a><span data-ttu-id="2e926-164">Funzioni di hosting</span><span class="sxs-lookup"><span data-stu-id="2e926-164">Hosting functions</span></span>  
 [<span data-ttu-id="2e926-165">Funzione CallFunctionShim</span><span class="sxs-lookup"><span data-stu-id="2e926-165">CallFunctionShim Function</span></span>](callfunctionshim-function.md)  
 <span data-ttu-id="2e926-166">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-166">Deprecated.</span></span> <span data-ttu-id="2e926-167">Esegue una chiamata alla funzione con il nome e i parametri specificati nella libreria specificata.</span><span class="sxs-lookup"><span data-stu-id="2e926-167">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 [<span data-ttu-id="2e926-168">Funzione CoEEShutDownCOM</span><span class="sxs-lookup"><span data-stu-id="2e926-168">CoEEShutDownCOM Function</span></span>](coeeshutdowncom-function.md)  
 <span data-ttu-id="2e926-169">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-169">Deprecated.</span></span> <span data-ttu-id="2e926-170">Scarica un assembly COM dal processo.</span><span class="sxs-lookup"><span data-stu-id="2e926-170">Unloads a COM assembly from the process.</span></span>  
  
 [<span data-ttu-id="2e926-171">Funzione CorExitProcess</span><span class="sxs-lookup"><span data-stu-id="2e926-171">CorExitProcess Function</span></span>](corexitprocess-function.md)  
 <span data-ttu-id="2e926-172">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-172">Deprecated.</span></span> <span data-ttu-id="2e926-173">Arresta il processo non gestito corrente.</span><span class="sxs-lookup"><span data-stu-id="2e926-173">Shuts down the current unmanaged process.</span></span>  
  
 [<span data-ttu-id="2e926-174">Funzione CorLaunchApplication</span><span class="sxs-lookup"><span data-stu-id="2e926-174">CorLaunchApplication Function</span></span>](corlaunchapplication-function.md)  
 <span data-ttu-id="2e926-175">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-175">Deprecated.</span></span> <span data-ttu-id="2e926-176">Avvia l'applicazione nel percorso di rete specificato, utilizzando i manifesti specificati e altri dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2e926-176">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 [<span data-ttu-id="2e926-177">Funzione CorMarkThreadInThreadPool</span><span class="sxs-lookup"><span data-stu-id="2e926-177">CorMarkThreadInThreadPool Function</span></span>](cormarkthreadinthreadpool-function.md)  
 <span data-ttu-id="2e926-178">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-178">Deprecated.</span></span> <span data-ttu-id="2e926-179">Contrassegna il thread del pool di thread attualmente in esecuzione per l'esecuzione del codice gestito.</span><span class="sxs-lookup"><span data-stu-id="2e926-179">Marks the currently executing thread-pool thread for the execution of managed code.</span></span> <span data-ttu-id="2e926-180">A partire da .NET Framework versione 2,0, questa funzione non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="2e926-180">Starting with the .NET Framework version 2.0, this function has no effect.</span></span> <span data-ttu-id="2e926-181">Non è obbligatorio e può essere rimosso dal codice.</span><span class="sxs-lookup"><span data-stu-id="2e926-181">It is not required, and can be removed from your code.</span></span>  
  
 [<span data-ttu-id="2e926-182">Funzione CoUninitializeCor</span><span class="sxs-lookup"><span data-stu-id="2e926-182">CoUninitializeCor Function</span></span>](couninitializecor-function.md)  
 <span data-ttu-id="2e926-183">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="2e926-183">Obsolete.</span></span> <span data-ttu-id="2e926-184">Non è possibile scaricare CLR da un processo.</span><span class="sxs-lookup"><span data-stu-id="2e926-184">The CLR cannot be unloaded from a process.</span></span>  
  
 [<span data-ttu-id="2e926-185">Funzione CoUninitializeEE</span><span class="sxs-lookup"><span data-stu-id="2e926-185">CoUninitializeEE Function</span></span>](couninitializeee-function.md)  
 <span data-ttu-id="2e926-186">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="2e926-186">Obsolete.</span></span>  
  
 [<span data-ttu-id="2e926-187">Funzione CreateDebuggingInterfaceFromVersion</span><span class="sxs-lookup"><span data-stu-id="2e926-187">CreateDebuggingInterfaceFromVersion Function</span></span>](createdebugginginterfacefromversion-function.md)  
 <span data-ttu-id="2e926-188">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-188">Deprecated.</span></span> <span data-ttu-id="2e926-189">Crea un oggetto [ICorDebug](../debugging/icordebug-interface.md) in base alle informazioni sulla versione specificate.</span><span class="sxs-lookup"><span data-stu-id="2e926-189">Creates an [ICorDebug](../debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 [<span data-ttu-id="2e926-190">Funzione CreateICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="2e926-190">CreateICeeFileGen Function</span></span>](createiceefilegen-function.md)  
 <span data-ttu-id="2e926-191">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-191">Deprecated.</span></span> <span data-ttu-id="2e926-192">Crea un oggetto [ICeeFileGen](iceefilegen-class.md) .</span><span class="sxs-lookup"><span data-stu-id="2e926-192">Creates an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="2e926-193">Funzione DestroyICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="2e926-193">DestroyICeeFileGen Function</span></span>](destroyiceefilegen-function.md)  
 <span data-ttu-id="2e926-194">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-194">Deprecated.</span></span> <span data-ttu-id="2e926-195">Elimina definitivamente un oggetto [ICeeFileGen](iceefilegen-class.md) .</span><span class="sxs-lookup"><span data-stu-id="2e926-195">Destroys an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="2e926-196">Puntatore alla funzione FExecuteInAppDomainCallback</span><span class="sxs-lookup"><span data-stu-id="2e926-196">FExecuteInAppDomainCallback Function Pointer</span></span>](fexecuteinappdomaincallback-function-pointer.md)  
 <span data-ttu-id="2e926-197">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-197">Deprecated.</span></span> <span data-ttu-id="2e926-198">Punta a una funzione chiamata da CLR per eseguire codice gestito.</span><span class="sxs-lookup"><span data-stu-id="2e926-198">Points to a function that the CLR calls to execute managed code.</span></span>  
  
 [<span data-ttu-id="2e926-199">Puntatore alla funzione FLockClrVersionCallback</span><span class="sxs-lookup"><span data-stu-id="2e926-199">FLockClrVersionCallback Function Pointer</span></span>](flockclrversioncallback-function-pointer.md)  
 <span data-ttu-id="2e926-200">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-200">Deprecated.</span></span> <span data-ttu-id="2e926-201">Punta a una funzione chiamata da CLR per notificare all'host che l'inizializzazione è stata avviata o completata.</span><span class="sxs-lookup"><span data-stu-id="2e926-201">Points to a function that the CLR calls to notify the host that initialization has either started or completed.</span></span>  
  
 [<span data-ttu-id="2e926-202">Funzione GetCLRIdentityManager</span><span class="sxs-lookup"><span data-stu-id="2e926-202">GetCLRIdentityManager Function</span></span>](getclridentitymanager-function.md)  
 <span data-ttu-id="2e926-203">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-203">Deprecated.</span></span> <span data-ttu-id="2e926-204">Ottiene un puntatore a un'interfaccia che consente a CLR di gestire le identità.</span><span class="sxs-lookup"><span data-stu-id="2e926-204">Gets a pointer to an interface that allows the CLR to manage identities.</span></span>  
  
 [<span data-ttu-id="2e926-205">Funzione LoadLibraryShim</span><span class="sxs-lookup"><span data-stu-id="2e926-205">LoadLibraryShim Function</span></span>](loadlibraryshim-function.md)  
 <span data-ttu-id="2e926-206">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-206">Deprecated.</span></span> <span data-ttu-id="2e926-207">Carica una versione specificata di una DLL .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2e926-207">Loads a specified version of a .NET Framework DLL.</span></span>  
  
 [<span data-ttu-id="2e926-208">Funzione LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="2e926-208">LoadStringRC Function</span></span>](loadstringrc-function.md)  
 <span data-ttu-id="2e926-209">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-209">Deprecated.</span></span> <span data-ttu-id="2e926-210">Converte un valore HRESULT in un messaggio di errore utilizzando le impostazioni cultura predefinite del thread corrente.</span><span class="sxs-lookup"><span data-stu-id="2e926-210">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 [<span data-ttu-id="2e926-211">Funzione LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="2e926-211">LoadStringRCEx Function</span></span>](loadstringrcex-function.md)  
 <span data-ttu-id="2e926-212">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-212">Deprecated.</span></span> <span data-ttu-id="2e926-213">Converte un valore HRESULT in un messaggio di errore appropriato per le impostazioni cultura specificate.</span><span class="sxs-lookup"><span data-stu-id="2e926-213">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 [<span data-ttu-id="2e926-214">Puntatore alla funzione LPOVERLAPPED_COMPLETION_ROUTINE</span><span class="sxs-lookup"><span data-stu-id="2e926-214">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>](lpoverlapped-completion-routine-function-pointer.md)  
 <span data-ttu-id="2e926-215">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-215">Deprecated.</span></span> <span data-ttu-id="2e926-216">Punta a una funzione che notifica all'host quando è stata completata un'operazione di I/O sovrapposta (ovvero asincrona) a un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2e926-216">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 [<span data-ttu-id="2e926-217">Puntatore alla funzione LPTHREAD_START_ROUTINE</span><span class="sxs-lookup"><span data-stu-id="2e926-217">LPTHREAD_START_ROUTINE Function Pointer</span></span>](lpthread-start-routine-function-pointer.md)  
 <span data-ttu-id="2e926-218">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-218">Deprecated.</span></span> <span data-ttu-id="2e926-219">Punta a una funzione che notifica all'host che un thread è stato avviato per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2e926-219">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 [<span data-ttu-id="2e926-220">Funzione RunDll32ShimW</span><span class="sxs-lookup"><span data-stu-id="2e926-220">RunDll32ShimW Function</span></span>](rundll32shimw-function.md)  
 <span data-ttu-id="2e926-221">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-221">Deprecated.</span></span> <span data-ttu-id="2e926-222">Esegue il comando specificato.</span><span class="sxs-lookup"><span data-stu-id="2e926-222">Executes the specified command.</span></span>  
  
 [<span data-ttu-id="2e926-223">Puntatore alla funzione WAITORTIMERCALLBACK</span><span class="sxs-lookup"><span data-stu-id="2e926-223">WAITORTIMERCALLBACK Function Pointer</span></span>](waitortimercallback-function-pointer.md)  
 <span data-ttu-id="2e926-224">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="2e926-224">Deprecated.</span></span> <span data-ttu-id="2e926-225">Punta a una funzione che notifica all'host che un handle di attesa è stato segnalato o si è verificato un timeout.</span><span class="sxs-lookup"><span data-stu-id="2e926-225">Points to a function that notifies the host that a wait handle has either been signaled or timed out.</span></span>  
  
## <a name="infrastructure-functions"></a><span data-ttu-id="2e926-226">Funzioni dell'infrastruttura</span><span class="sxs-lookup"><span data-stu-id="2e926-226">Infrastructure functions</span></span>  
 <span data-ttu-id="2e926-227">Le funzioni in questa sezione sono utilizzate solo dal .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2e926-227">The functions in this section are for use by the .NET Framework only.</span></span>  
  
 [<span data-ttu-id="2e926-228">Funzione _CorDllMain</span><span class="sxs-lookup"><span data-stu-id="2e926-228">_CorDllMain Function</span></span>](cordllmain-function.md)  
 <span data-ttu-id="2e926-229">Inizializza CLR, individua il punto di ingresso gestito nell'intestazione CLR dell'assembly DLL e avvia l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2e926-229">Initializes the CLR, locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="2e926-230">Funzione _CorExeMain</span><span class="sxs-lookup"><span data-stu-id="2e926-230">_CorExeMain Function</span></span>](corexemain-function.md)  
 <span data-ttu-id="2e926-231">Inizializza CLR, individua il punto di ingresso gestito nell'intestazione CLR dell'assembly eseguibile e avvia l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2e926-231">Initializes the CLR, locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="2e926-232">Funzione _CorExeMain2</span><span class="sxs-lookup"><span data-stu-id="2e926-232">_CorExeMain2 Function</span></span>](corexemain2-function.md)  
 <span data-ttu-id="2e926-233">Esegue il punto di ingresso nel codice mappato alla memoria specificato.</span><span class="sxs-lookup"><span data-stu-id="2e926-233">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="2e926-234">Questa funzione viene chiamata dal caricatore del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="2e926-234">This function is called by the operating system loader.</span></span>  
  
 [<span data-ttu-id="2e926-235">Funzione _CorImageUnloading</span><span class="sxs-lookup"><span data-stu-id="2e926-235">_CorImageUnloading Function</span></span>](corimageunloading-function.md)  
 <span data-ttu-id="2e926-236">Notifica al caricatore quando le immagini del modulo gestito vengono scaricate.</span><span class="sxs-lookup"><span data-stu-id="2e926-236">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 [<span data-ttu-id="2e926-237">Funzione _CorValidateImage</span><span class="sxs-lookup"><span data-stu-id="2e926-237">_CorValidateImage Function</span></span>](corvalidateimage-function.md)  
 <span data-ttu-id="2e926-238">Convalida le immagini del modulo gestito e invia una notifica al caricatore del sistema operativo dopo che sono state caricate.</span><span class="sxs-lookup"><span data-stu-id="2e926-238">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e926-239">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e926-239">See also</span></span>

- [<span data-ttu-id="2e926-240">Funzioni statiche globali di hosting di .NET Framework 4</span><span class="sxs-lookup"><span data-stu-id="2e926-240">.NET Framework 4 Hosting Global Static Functions</span></span>](net-framework-4-hosting-global-static-functions.md)

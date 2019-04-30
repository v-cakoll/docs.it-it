---
title: Funzione CorBindToRuntimeEx
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeEx
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeEx
helpviewer_keywords:
- CorBindToRuntimeEx function [.NET Framework hosting]
ms.assetid: aae9fb17-5d01-41da-9773-1b5b5b642d81
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7bc409d409cd4da54b61b16d069ce50c2456b53d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985843"
---
# <a name="corbindtoruntimeex-function"></a><span data-ttu-id="4759b-102">Funzione CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="4759b-102">CorBindToRuntimeEx Function</span></span>
<span data-ttu-id="4759b-103">Consente l'host non gestiti di caricare common language runtime (CLR) in un processo.</span><span class="sxs-lookup"><span data-stu-id="4759b-103">Enables unmanaged hosts to load the common language runtime (CLR) into a process.</span></span> <span data-ttu-id="4759b-104">Il [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) e `CorBindToRuntimeEx` funzioni eseguono la stessa operazione, ma il `CorBindToRuntimeEx` funzione consente di impostare i flag per specificare il comportamento di CLR.</span><span class="sxs-lookup"><span data-stu-id="4759b-104">The [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) and `CorBindToRuntimeEx` functions perform the same operation, but the `CorBindToRuntimeEx` function allows you to set flags to specify the behavior of the CLR.</span></span>  
  
 <span data-ttu-id="4759b-105">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4759b-105">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
 <span data-ttu-id="4759b-106">Questa funzione accetta un set di parametri che consentono a un host eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4759b-106">This function takes a set of parameters that allow a host to do the following:</span></span>  
  
- <span data-ttu-id="4759b-107">Specificare la versione del runtime che verrà caricato.</span><span class="sxs-lookup"><span data-stu-id="4759b-107">Specify the version of the runtime that will be loaded.</span></span>  
  
- <span data-ttu-id="4759b-108">Indicare se la compilazione di server o workstation deve essere caricata.</span><span class="sxs-lookup"><span data-stu-id="4759b-108">Indicate whether the server or workstation build should be loaded.</span></span>  
  
- <span data-ttu-id="4759b-109">Controllare se l'operazione garbage collection simultanea o non simultanea operazione di garbage collection viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="4759b-109">Control whether concurrent garbage collection or non-concurrent garbage collection is done.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4759b-110">Garbage collection simultanea non è supportata nelle applicazioni in esecuzione WOW64 x86 dell'emulatore su sistemi a 64 bit che implementino l'architettura Intel Itanium (in precedenza denominato IA-64).</span><span class="sxs-lookup"><span data-stu-id="4759b-110">Concurrent garbage collection is not supported in applications running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="4759b-111">Per altre informazioni sull'utilizzo di WOW64 nei sistemi Windows a 64 bit, vedere [delle applicazioni in esecuzione a 32 bit](/windows/desktop/WinProg64/running-32-bit-applications).</span><span class="sxs-lookup"><span data-stu-id="4759b-111">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](/windows/desktop/WinProg64/running-32-bit-applications).</span></span>  
  
- <span data-ttu-id="4759b-112">Controllare se gli assembly vengono caricati come indipendenti dal dominio.</span><span class="sxs-lookup"><span data-stu-id="4759b-112">Control whether assemblies are loaded as domain-neutral.</span></span>  
  
- <span data-ttu-id="4759b-113">Ottenere un puntatore a interfaccia a un [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) che può essere utilizzato per impostare opzioni aggiuntive per la configurazione di un'istanza di Common Language Runtime prima che venga avviato.</span><span class="sxs-lookup"><span data-stu-id="4759b-113">Obtain an interface pointer to an [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) that can be used to set additional options for configuring an instance of the CLR before it is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4759b-114">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4759b-114">Syntax</span></span>  
  
```  
HRESULT CorBindToRuntimeEx (  
    [in]  LPCWSTR      pwszVersion,   
    [in]  LPCWSTR      pwszBuildFlavor,   
    [in]  DWORD        startupFlags,   
    [in]  REFCLSID     rclsid,   
    [in]  REFIID       riid,   
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4759b-115">Parametri</span><span class="sxs-lookup"><span data-stu-id="4759b-115">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="4759b-116">[in] Stringa che descrive la versione di CLR a cui si desidera caricare.</span><span class="sxs-lookup"><span data-stu-id="4759b-116">[in] A string describing the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="4759b-117">Un numero di versione in .NET Framework è costituito da quattro parti separate da punti: *revisione*.</span><span class="sxs-lookup"><span data-stu-id="4759b-117">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="4759b-118">La stringa passata come `pwszVersion` deve iniziare con il carattere "v" seguito dalle prime tre parti del numero di versione (ad esempio, "v 1.0.1529").</span><span class="sxs-lookup"><span data-stu-id="4759b-118">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="4759b-119">Alcune versioni di CLR installate con un'istruzione di criteri che specifica la compatibilità con le versioni precedenti di CLR.</span><span class="sxs-lookup"><span data-stu-id="4759b-119">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="4759b-120">Per impostazione predefinita, valuta lo shim di avvio `pwszVersion` contro le istruzioni dei criteri e carichi la versione più recente del runtime che è compatibile con la versione richiesta.</span><span class="sxs-lookup"><span data-stu-id="4759b-120">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="4759b-121">Un host può forzare lo shim per ignorare la valutazione dei criteri e caricare la versione esatta specificata nel `pwszVersion` passando un valore di `STARTUP_LOADER_SAFEMODE` per il `startupFlags` parametro, come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="4759b-121">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of  `STARTUP_LOADER_SAFEMODE` for the `startupFlags` parameter, as described below.</span></span>  
  
 <span data-ttu-id="4759b-122">Se il chiamante specifica null per `pwszVersion`, `CorBindToRuntimeEx` identifica il set di runtime installati cui numeri di versione sono inferiori al runtime di .NET Framework 4 e carica la versione più recente del runtime da tale set.</span><span class="sxs-lookup"><span data-stu-id="4759b-122">If the caller specifies null for `pwszVersion`, `CorBindToRuntimeEx` identifies the set of installed runtimes whose version numbers are lower than the .NET Framework 4 runtime, and loads the latest version of the runtime from that set.</span></span> <span data-ttu-id="4759b-123">Non caricherà il .NET Framework 4 o versione successiva e non riesce se non è installata alcuna versione precedente.</span><span class="sxs-lookup"><span data-stu-id="4759b-123">It won't load the .NET Framework 4 or later, and fails if no earlier version is installed.</span></span> <span data-ttu-id="4759b-124">Si noti che il passaggio di null non consente all'host di alcun controllo sulla quale versione del runtime è caricata.</span><span class="sxs-lookup"><span data-stu-id="4759b-124">Note that passing null gives the host no control over which version of the runtime is loaded.</span></span> <span data-ttu-id="4759b-125">Sebbene questo approccio potrebbe essere appropriato in alcuni scenari, è consigliabile che l'host di fornisca una versione specifica di caricare.</span><span class="sxs-lookup"><span data-stu-id="4759b-125">Although this approach may be appropriate in some scenarios, it is strongly recommended that the host supply a specific version to load.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="4759b-126">[in] Stringa che specifica se caricare il server o la compilazione di workstation di CLR.</span><span class="sxs-lookup"><span data-stu-id="4759b-126">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="4759b-127">I valori validi sono `svr` e `wks`.</span><span class="sxs-lookup"><span data-stu-id="4759b-127">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="4759b-128">La compilazione di server è ottimizzata per sfruttare più processori per operazioni di garbage collection e la compilazione di workstation è ottimizzata per le applicazioni client in esecuzione in un computer a processore singolo.</span><span class="sxs-lookup"><span data-stu-id="4759b-128">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="4759b-129">Se `pwszBuildFlavor` è impostato su null, la compilazione di workstation viene caricata.</span><span class="sxs-lookup"><span data-stu-id="4759b-129">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="4759b-130">Durante l'esecuzione in un computer a processore singolo, la compilazione di workstation viene sempre caricata, anche se `pwszBuildFlavor` è impostata su `svr`.</span><span class="sxs-lookup"><span data-stu-id="4759b-130">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="4759b-131">Tuttavia, se `pwszBuildFlavor` è impostata su `svr` e garbage collection simultanea è specificata (vedere la descrizione del `startupFlags` parametro), viene caricata la compilazione di server.</span><span class="sxs-lookup"><span data-stu-id="4759b-131">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `startupFlags` parameter), the server build is loaded.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="4759b-132">[in] Una combinazione di valori del [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumerazione.</span><span class="sxs-lookup"><span data-stu-id="4759b-132">[in] A combination of values of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration.</span></span> <span data-ttu-id="4759b-133">Questi flag controllano il comportamento di garbage collection simultanea e il codice indipendente dal dominio la `pwszVersion` parametro.</span><span class="sxs-lookup"><span data-stu-id="4759b-133">These flags control concurrent garbage collection, domain-neutral code, and the behavior of the `pwszVersion` parameter.</span></span> <span data-ttu-id="4759b-134">Se non è impostato alcun flag, il valore predefinito è singolo dominio.</span><span class="sxs-lookup"><span data-stu-id="4759b-134">The default is single domain if no flag is set.</span></span> <span data-ttu-id="4759b-135">Di seguito vengono illustrati i valori validi.</span><span class="sxs-lookup"><span data-stu-id="4759b-135">The following values are valid:</span></span>  
  
- `STARTUP_CONCURRENT_GC`  
  
- `STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN`  
  
- `STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN`  
  
- `STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST`  
  
- `STARTUP_LOADER_SAFEMODE`  
  
- `STARTUP_LEGACY_IMPERSONATION`  
  
- `STARTUP_LOADER_SETPREFERENCE`  
  
- `STARTUP_SERVER_GC`  
  
- `STARTUP_HOARD_GC_VM`  
  
- `STARTUP_SINGLE_VERSION_HOSTING_INTERFACE`  
  
- `STARTUP_LEGACY_IMPERSONATION`  
  
- `STARTUP_DISABLE_COMMITTHREADSTACK`  
  
- `STARTUP_ALWAYSFLOW_IMPERSONATION`  
  
 <span data-ttu-id="4759b-136">Per una descrizione di questi flag, vedere la [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumerazione.</span><span class="sxs-lookup"><span data-stu-id="4759b-136">For descriptions of these flags, see the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="4759b-137">[in] Il `CLSID` della coclasse che implementa il [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) o il [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="4759b-137">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="4759b-138">I valori supportati sono CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="4759b-138">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="4759b-139">[in] Il `IID` dell'interfaccia richiesta da `rclsid`.</span><span class="sxs-lookup"><span data-stu-id="4759b-139">[in] The `IID` of the requested interface from `rclsid`.</span></span> <span data-ttu-id="4759b-140">Valori supportati sono IID_ICorRuntimeHost o IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="4759b-140">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="4759b-141">[out] Il puntatore a interfaccia restituito `riid`.</span><span class="sxs-lookup"><span data-stu-id="4759b-141">[out] The returned interface pointer to `riid`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4759b-142">Note</span><span class="sxs-lookup"><span data-stu-id="4759b-142">Remarks</span></span>  
 <span data-ttu-id="4759b-143">Se `pwszVersion` specifica una versione di runtime che non esiste, `CorBindToRuntimeEx` restituisce un valore HRESULT di CLR_E_SHIM_RUNTIMELOAD.</span><span class="sxs-lookup"><span data-stu-id="4759b-143">If `pwszVersion` specifies a runtime version that does not exist, `CorBindToRuntimeEx` returns an HRESULT value of CLR_E_SHIM_RUNTIMELOAD.</span></span>  
  
## <a name="execution-context-and-flow-of-windows-identity"></a><span data-ttu-id="4759b-144">Contesto di esecuzione e il flusso dell'identità di Windows</span><span class="sxs-lookup"><span data-stu-id="4759b-144">Execution Context and Flow of Windows Identity</span></span>  
 <span data-ttu-id="4759b-145">Nella versione 1 di CLR, il <xref:System.Security.Principal.WindowsIdentity> oggetto non passa attraverso punti asincroni, ad esempio nuovi thread, i pool di thread o i callback di timer.</span><span class="sxs-lookup"><span data-stu-id="4759b-145">In version 1 of the CLR, the <xref:System.Security.Principal.WindowsIdentity> object does not flow across asynchronous points such as new threads, thread pools, or timer callbacks.</span></span> <span data-ttu-id="4759b-146">Nella versione 2.0 di CLR, un <xref:System.Threading.ExecutionContext> oggetto esegue il wrapping di alcune informazioni relative al thread attualmente in esecuzione e ne effettua attraverso punti asincroni qualsiasi, ma non tra i limiti del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="4759b-146">In version 2.0 of the CLR, an <xref:System.Threading.ExecutionContext> object wraps some information about the currently executing thread and flows it across any asynchronous point, but not across application domain boundaries.</span></span> <span data-ttu-id="4759b-147">Analogamente, il <xref:System.Security.Principal.WindowsIdentity> oggetto anche passa attraverso punti asincroni qualsiasi.</span><span class="sxs-lookup"><span data-stu-id="4759b-147">Similarly, the <xref:System.Security.Principal.WindowsIdentity> object also flows across any asynchronous point.</span></span> <span data-ttu-id="4759b-148">Pertanto, la rappresentazione corrente nel thread, se presente, flussi troppo.</span><span class="sxs-lookup"><span data-stu-id="4759b-148">Therefore, the current impersonation on the thread, if any, flows too.</span></span>  
  
 <span data-ttu-id="4759b-149">È possibile modificare il flusso in due modi:</span><span class="sxs-lookup"><span data-stu-id="4759b-149">You can alter the flow in two ways:</span></span>  
  
1. <span data-ttu-id="4759b-150">Modificando la <xref:System.Threading.ExecutionContext> le impostazioni per sopprimere il flusso in un singolo thread (vedere la <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, e <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> metodi).</span><span class="sxs-lookup"><span data-stu-id="4759b-150">By modifying the <xref:System.Threading.ExecutionContext> settings to suppress the flow on a per-thread basis (see the <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, and <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> methods).</span></span>  
  
2. <span data-ttu-id="4759b-151">Modificando la modalità predefinita del processo per la modalità di compatibilità di versione 1, in cui il <xref:System.Security.Principal.WindowsIdentity> oggetto non passa attraverso punti asincroni, qualsiasi indipendentemente il <xref:System.Threading.ExecutionContext> impostazioni sul thread corrente.</span><span class="sxs-lookup"><span data-stu-id="4759b-151">By changing the process default mode to the version 1 compatibility mode, where the <xref:System.Security.Principal.WindowsIdentity> object does not flow across any asynchronous point, regardless of the <xref:System.Threading.ExecutionContext> settings on the current thread.</span></span> <span data-ttu-id="4759b-152">Come si modifica la modalità predefinita varia a seconda se si usa un file eseguibile gestito o un'interfaccia di hosting non gestita per caricamento di CLR:</span><span class="sxs-lookup"><span data-stu-id="4759b-152">How you change the default mode depends on whether you use a managed executable or an unmanaged hosting interface to load the CLR:</span></span>  
  
    1. <span data-ttu-id="4759b-153">Per gli eseguibili gestiti, è necessario impostare il `enabled` attributo del [ \<legacyImpersonationPolicy >](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) elemento `true`.</span><span class="sxs-lookup"><span data-stu-id="4759b-153">For managed executables, you must set the `enabled` attribute of the [\<legacyImpersonationPolicy>](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) element to `true`.</span></span>  
  
    2. <span data-ttu-id="4759b-154">Per non gestiti di interfacce di hosting, impostare il `STARTUP_LEGACY_IMPERSONATION` flag nel `startupFlags` parametro quando si chiama il `CorBindToRuntimeEx` (funzione).</span><span class="sxs-lookup"><span data-stu-id="4759b-154">For unmanaged hosting interfaces, set the `STARTUP_LEGACY_IMPERSONATION` flag in the `startupFlags` parameter when calling the `CorBindToRuntimeEx` function.</span></span>  
  
     <span data-ttu-id="4759b-155">La modalità di compatibilità di versione 1 si applica all'intero processo e per tutti i domini applicazione nel processo.</span><span class="sxs-lookup"><span data-stu-id="4759b-155">The version 1 compatibility mode applies to the entire process and to all the application domains in the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4759b-156">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4759b-156">Requirements</span></span>  
 <span data-ttu-id="4759b-157">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4759b-157">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4759b-158">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4759b-158">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4759b-159">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4759b-159">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4759b-160">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4759b-160">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4759b-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4759b-161">See also</span></span>

- [<span data-ttu-id="4759b-162">Funzione CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="4759b-162">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="4759b-163">Funzione CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="4759b-163">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [<span data-ttu-id="4759b-164">Funzione CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="4759b-164">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="4759b-165">Funzione CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="4759b-165">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [<span data-ttu-id="4759b-166">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="4759b-166">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="4759b-167">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="4759b-167">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

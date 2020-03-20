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
ms.openlocfilehash: 3520af5f55f43183920dce7fbd24b70359c023a2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176500"
---
# <a name="corbindtoruntimeex-function"></a><span data-ttu-id="22615-102">Funzione CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="22615-102">CorBindToRuntimeEx Function</span></span>
<span data-ttu-id="22615-103">Consente agli host non gestiti di caricare Common Language Runtime (CLR) in un processo.</span><span class="sxs-lookup"><span data-stu-id="22615-103">Enables unmanaged hosts to load the common language runtime (CLR) into a process.</span></span> <span data-ttu-id="22615-104">Le funzioni [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) e `CorBindToRuntimeEx` eseguono `CorBindToRuntimeEx` la stessa operazione, ma la funzione consente di impostare flag per specificare il comportamento di CLR.</span><span class="sxs-lookup"><span data-stu-id="22615-104">The [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) and `CorBindToRuntimeEx` functions perform the same operation, but the `CorBindToRuntimeEx` function allows you to set flags to specify the behavior of the CLR.</span></span>  
  
 <span data-ttu-id="22615-105">Questa funzione è stata deprecata in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="22615-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
 <span data-ttu-id="22615-106">Questa funzione accetta un set di parametri che consentono a un host di eseguire le operazioni seguenti:This function takes a set of parameters that allow a host to do the following:</span><span class="sxs-lookup"><span data-stu-id="22615-106">This function takes a set of parameters that allow a host to do the following:</span></span>  
  
- <span data-ttu-id="22615-107">Specificare la versione del runtime che verrà caricata.</span><span class="sxs-lookup"><span data-stu-id="22615-107">Specify the version of the runtime that will be loaded.</span></span>  
  
- <span data-ttu-id="22615-108">Indicare se la build del server o della workstation deve essere caricata.</span><span class="sxs-lookup"><span data-stu-id="22615-108">Indicate whether the server or workstation build should be loaded.</span></span>  
  
- <span data-ttu-id="22615-109">Controllare se viene eseguita l'operazione di Garbage Collection simultanea o non simultanea.</span><span class="sxs-lookup"><span data-stu-id="22615-109">Control whether concurrent garbage collection or non-concurrent garbage collection is done.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="22615-110">La Garbage Collection simultanea non è supportata nelle applicazioni che eseguono l'emulatore WOW64 x86 su sistemi a 64 bit che implementano l'architettura Intel Itanium (precedentemente denominata IA-64).</span><span class="sxs-lookup"><span data-stu-id="22615-110">Concurrent garbage collection is not supported in applications running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="22615-111">Per ulteriori informazioni sull'utilizzo di WOW64 nei sistemi Windows a 64 bit, vedere Esecuzione di applicazioni a [32 bit](/windows/desktop/WinProg64/running-32-bit-applications).</span><span class="sxs-lookup"><span data-stu-id="22615-111">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](/windows/desktop/WinProg64/running-32-bit-applications).</span></span>  
  
- <span data-ttu-id="22615-112">Controllare se gli assembly vengono caricati come indipendenti dal dominio.</span><span class="sxs-lookup"><span data-stu-id="22615-112">Control whether assemblies are loaded as domain-neutral.</span></span>  
  
- <span data-ttu-id="22615-113">Ottenere un puntatore a interfaccia a un [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) che può essere utilizzato per impostare opzioni aggiuntive per la configurazione di un'istanza di CLR prima che venga avviato.</span><span class="sxs-lookup"><span data-stu-id="22615-113">Obtain an interface pointer to an [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) that can be used to set additional options for configuring an instance of the CLR before it is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22615-114">Sintassi</span><span class="sxs-lookup"><span data-stu-id="22615-114">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToRuntimeEx (  
    [in]  LPCWSTR      pwszVersion,
    [in]  LPCWSTR      pwszBuildFlavor,
    [in]  DWORD        startupFlags,
    [in]  REFCLSID     rclsid,
    [in]  REFIID       riid,
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22615-115">Parametri</span><span class="sxs-lookup"><span data-stu-id="22615-115">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="22615-116">[in] Stringa che descrive la versione di CLR che si desidera caricare.</span><span class="sxs-lookup"><span data-stu-id="22615-116">[in] A string describing the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="22615-117">Un numero di versione in .NET Framework è costituito da quattro parti separate da punti: *major.minor.build.revision*.</span><span class="sxs-lookup"><span data-stu-id="22615-117">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="22615-118">La stringa `pwszVersion` passata come deve iniziare con il carattere "v" seguito dalle prime tre parti del numero di versione (ad esempio, "v1.0.1529").</span><span class="sxs-lookup"><span data-stu-id="22615-118">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="22615-119">Alcune versioni di CLR vengono installate con un'istruzione dei criteri che specifica la compatibilità con le versioni precedenti di CLR.</span><span class="sxs-lookup"><span data-stu-id="22615-119">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="22615-120">Per impostazione predefinita, lo `pwszVersion` shim di avvio valuta rispetto alle istruzioni dei criteri e carica la versione più recente del runtime compatibile con la versione richiesta.</span><span class="sxs-lookup"><span data-stu-id="22615-120">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="22615-121">Un host può forzare lo shim a ignorare `pwszVersion` la valutazione dei `STARTUP_LOADER_SAFEMODE` criteri `startupFlags` e caricare la versione esatta specificata in passando un valore di per il parametro, come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="22615-121">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of  `STARTUP_LOADER_SAFEMODE` for the `startupFlags` parameter, as described below.</span></span>  
  
 <span data-ttu-id="22615-122">Se il chiamante `pwszVersion`specifica `CorBindToRuntimeEx` null per , identifica il set di runtime installati i cui numeri di versione sono inferiori al runtime di .NET Framework 4 e carica la versione più recente del runtime da tale set.</span><span class="sxs-lookup"><span data-stu-id="22615-122">If the caller specifies null for `pwszVersion`, `CorBindToRuntimeEx` identifies the set of installed runtimes whose version numbers are lower than the .NET Framework 4 runtime, and loads the latest version of the runtime from that set.</span></span> <span data-ttu-id="22615-123">Non caricherà .NET Framework 4 o versione successiva e non riesce se non è installata alcuna versione precedente.</span><span class="sxs-lookup"><span data-stu-id="22615-123">It won't load the .NET Framework 4 or later, and fails if no earlier version is installed.</span></span> <span data-ttu-id="22615-124">Si noti che il passaggio di null non fornisce all'host alcun controllo sulla versione del runtime caricata.</span><span class="sxs-lookup"><span data-stu-id="22615-124">Note that passing null gives the host no control over which version of the runtime is loaded.</span></span> <span data-ttu-id="22615-125">Anche se questo approccio può essere appropriato in alcuni scenari, è consigliabile che l'host fornisse una versione specifica da caricare.</span><span class="sxs-lookup"><span data-stu-id="22615-125">Although this approach may be appropriate in some scenarios, it is strongly recommended that the host supply a specific version to load.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="22615-126">[in] Stringa che specifica se caricare il server o la build della workstation di CLR.</span><span class="sxs-lookup"><span data-stu-id="22615-126">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="22615-127">I valori validi sono `svr` e `wks`.</span><span class="sxs-lookup"><span data-stu-id="22615-127">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="22615-128">La build server è ottimizzata per sfruttare più processori per le operazioni di Garbage Collection e la build workstation è ottimizzata per le applicazioni client in esecuzione su un computer a processore singolo.</span><span class="sxs-lookup"><span data-stu-id="22615-128">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="22615-129">Se `pwszBuildFlavor` è impostato su null, viene caricata la build della workstation.</span><span class="sxs-lookup"><span data-stu-id="22615-129">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="22615-130">Quando viene eseguita su un computer a processore singolo, la build della workstation viene sempre caricata, anche se `pwszBuildFlavor` è impostata su `svr`.</span><span class="sxs-lookup"><span data-stu-id="22615-130">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="22615-131">Tuttavia, `pwszBuildFlavor` se `svr` è impostata su e viene specificata `startupFlags` l'operazione di Garbage Collection simultanea (vedere la descrizione del parametro), viene caricata la compilazione del server.</span><span class="sxs-lookup"><span data-stu-id="22615-131">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `startupFlags` parameter), the server build is loaded.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="22615-132">[in] Combinazione di valori dell'enumerazione [STARTUP_FLAGS.](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="22615-132">[in] A combination of values of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration.</span></span> <span data-ttu-id="22615-133">Questi flag controllano la Garbage Collection simultanea, il `pwszVersion` codice indipendente dal dominio e il comportamento del parametro.</span><span class="sxs-lookup"><span data-stu-id="22615-133">These flags control concurrent garbage collection, domain-neutral code, and the behavior of the `pwszVersion` parameter.</span></span> <span data-ttu-id="22615-134">Il valore predefinito è dominio singolo se non è impostato alcun flag.</span><span class="sxs-lookup"><span data-stu-id="22615-134">The default is single domain if no flag is set.</span></span> <span data-ttu-id="22615-135">I valori seguenti sono validi:</span><span class="sxs-lookup"><span data-stu-id="22615-135">The following values are valid:</span></span>  
  
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
  
 <span data-ttu-id="22615-136">Per le descrizioni di questi flag, vedere l'enumerazione [STARTUP_FLAGS.](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="22615-136">For descriptions of these flags, see the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="22615-137">[in] La `CLSID` della coclasse che implementa il [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) o [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="22615-137">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="22615-138">I valori supportati sono CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="22615-138">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="22615-139">[in] L'interfaccia `IID` richiesta `rclsid`da .</span><span class="sxs-lookup"><span data-stu-id="22615-139">[in] The `IID` of the requested interface from `rclsid`.</span></span> <span data-ttu-id="22615-140">I valori supportati sono IID_ICorRuntimeHost o IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="22615-140">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="22615-141">[fuori] Puntatore a interfaccia `riid`restituito a .</span><span class="sxs-lookup"><span data-stu-id="22615-141">[out] The returned interface pointer to `riid`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22615-142">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="22615-142">Remarks</span></span>  
 <span data-ttu-id="22615-143">Se `pwszVersion` specifica una versione di runtime `CorBindToRuntimeEx` che non esiste, restituisce un valore HRESULT di CLR_E_SHIM_RUNTIMELOAD.</span><span class="sxs-lookup"><span data-stu-id="22615-143">If `pwszVersion` specifies a runtime version that does not exist, `CorBindToRuntimeEx` returns an HRESULT value of CLR_E_SHIM_RUNTIMELOAD.</span></span>  
  
## <a name="execution-context-and-flow-of-windows-identity"></a><span data-ttu-id="22615-144">Contesto di esecuzione e flusso dell'identità di WindowsExecution Context and Flow of Windows Identity</span><span class="sxs-lookup"><span data-stu-id="22615-144">Execution Context and Flow of Windows Identity</span></span>  
 <span data-ttu-id="22615-145">Nella versione 1 di <xref:System.Security.Principal.WindowsIdentity> CLR, l'oggetto non passa attraverso punti asincroni, ad esempio nuovi thread, pool di thread o callback del timer.</span><span class="sxs-lookup"><span data-stu-id="22615-145">In version 1 of the CLR, the <xref:System.Security.Principal.WindowsIdentity> object does not flow across asynchronous points such as new threads, thread pools, or timer callbacks.</span></span> <span data-ttu-id="22615-146">Nella versione 2.0 di <xref:System.Threading.ExecutionContext> CLR, un oggetto esegue il wrapping di alcune informazioni sul thread attualmente in esecuzione e lo scorre attraverso qualsiasi punto asincrono, ma non attraverso i limiti del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="22615-146">In version 2.0 of the CLR, an <xref:System.Threading.ExecutionContext> object wraps some information about the currently executing thread and flows it across any asynchronous point, but not across application domain boundaries.</span></span> <span data-ttu-id="22615-147">Analogamente, <xref:System.Security.Principal.WindowsIdentity> l'oggetto scorre anche attraverso qualsiasi punto asincrono.</span><span class="sxs-lookup"><span data-stu-id="22615-147">Similarly, the <xref:System.Security.Principal.WindowsIdentity> object also flows across any asynchronous point.</span></span> <span data-ttu-id="22615-148">Pertanto, la rappresentazione corrente nel thread, se presente, scorre troppo.</span><span class="sxs-lookup"><span data-stu-id="22615-148">Therefore, the current impersonation on the thread, if any, flows too.</span></span>  
  
 <span data-ttu-id="22615-149">È possibile modificare il flusso in due modi:</span><span class="sxs-lookup"><span data-stu-id="22615-149">You can alter the flow in two ways:</span></span>  
  
1. <span data-ttu-id="22615-150">Modificando le <xref:System.Threading.ExecutionContext> impostazioni per sopprimere il flusso <xref:System.Threading.ExecutionContext.SuppressFlow%2A>in <xref:System.Security.SecurityContext.SuppressFlow%2A>base <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> al thread (vedere i metodi , e ).</span><span class="sxs-lookup"><span data-stu-id="22615-150">By modifying the <xref:System.Threading.ExecutionContext> settings to suppress the flow on a per-thread basis (see the <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, and <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> methods).</span></span>  
  
2. <span data-ttu-id="22615-151">Modificando la modalità predefinita del processo alla <xref:System.Security.Principal.WindowsIdentity> modalità di compatibilità della versione 1, in cui l'oggetto non passa attraverso alcun punto asincrono, indipendentemente dalle <xref:System.Threading.ExecutionContext> impostazioni nel thread corrente.</span><span class="sxs-lookup"><span data-stu-id="22615-151">By changing the process default mode to the version 1 compatibility mode, where the <xref:System.Security.Principal.WindowsIdentity> object does not flow across any asynchronous point, regardless of the <xref:System.Threading.ExecutionContext> settings on the current thread.</span></span> <span data-ttu-id="22615-152">La modalità di modifica della modalità predefinita dipende dall'utilizzo di un eseguibile gestito o di un'interfaccia di hosting non gestita per caricare CLR:</span><span class="sxs-lookup"><span data-stu-id="22615-152">How you change the default mode depends on whether you use a managed executable or an unmanaged hosting interface to load the CLR:</span></span>  
  
    1. <span data-ttu-id="22615-153">Per gli eseguibili gestiti, è necessario impostare l'attributo `enabled` dell'elemento `true` [ \<legacyImpersonationPolicy>](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) su .</span><span class="sxs-lookup"><span data-stu-id="22615-153">For managed executables, you must set the `enabled` attribute of the [\<legacyImpersonationPolicy>](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) element to `true`.</span></span>  
  
    2. <span data-ttu-id="22615-154">Per le interfacce di `STARTUP_LEGACY_IMPERSONATION` hosting non `startupFlags` gestite, `CorBindToRuntimeEx` impostare il flag nel parametro quando si chiama la funzione.</span><span class="sxs-lookup"><span data-stu-id="22615-154">For unmanaged hosting interfaces, set the `STARTUP_LEGACY_IMPERSONATION` flag in the `startupFlags` parameter when calling the `CorBindToRuntimeEx` function.</span></span>  
  
     <span data-ttu-id="22615-155">La modalità di compatibilità versione 1 si applica all'intero processo e a tutti i domini applicazione del processo.</span><span class="sxs-lookup"><span data-stu-id="22615-155">The version 1 compatibility mode applies to the entire process and to all the application domains in the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22615-156">Requisiti</span><span class="sxs-lookup"><span data-stu-id="22615-156">Requirements</span></span>  
 <span data-ttu-id="22615-157">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22615-157">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22615-158">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="22615-158">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="22615-159">**Biblioteca:** Mscoree</span><span class="sxs-lookup"><span data-stu-id="22615-159">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="22615-160">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22615-160">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22615-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22615-161">See also</span></span>

- [<span data-ttu-id="22615-162">Funzione CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="22615-162">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="22615-163">Funzione CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="22615-163">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [<span data-ttu-id="22615-164">Funzione CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="22615-164">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="22615-165">Funzione CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="22615-165">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [<span data-ttu-id="22615-166">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="22615-166">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="22615-167">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="22615-167">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

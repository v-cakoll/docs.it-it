---
title: Funzione CorBindToRuntime
ms.date: 03/30/2017
api_name:
- CorBindToRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntime
helpviewer_keywords:
- CorBindToRuntime function [.NET Framework hosting]
ms.assetid: 799740aa-46ec-4532-95da-6444565b4971
topic_type:
- apiref
ms.openlocfilehash: 2db9d26ef2dec150977c468b16334a7cb4b3d49c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176513"
---
# <a name="corbindtoruntime-function"></a><span data-ttu-id="d3a18-102">Funzione CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="d3a18-102">CorBindToRuntime Function</span></span>
<span data-ttu-id="d3a18-103">Consente agli host non gestiti di caricare Common Language Runtime (CLR) in un processo.</span><span class="sxs-lookup"><span data-stu-id="d3a18-103">Enables unmanaged hosts to load the common language runtime (CLR) into a process.</span></span>  
  
 <span data-ttu-id="d3a18-104">Questa funzione è stata deprecata in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d3a18-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3a18-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d3a18-105">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToRuntime (  
    [in]  LPCWSTR     pwszVersion,
    [in]  LPCWSTR     pwszBuildFlavor,
    [in]  REFCLSID    rclsid,
    [in]  REFIID      riid,
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3a18-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="d3a18-106">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="d3a18-107">[in] Stringa che descrive la versione di CLR che si desidera caricare.</span><span class="sxs-lookup"><span data-stu-id="d3a18-107">[in] A string describing the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="d3a18-108">Un numero di versione in .NET Framework è costituito da quattro parti separate da punti: *major.minor.build.revision*.</span><span class="sxs-lookup"><span data-stu-id="d3a18-108">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="d3a18-109">La stringa `pwszVersion` passata come deve iniziare con il carattere "v" seguito dalle prime tre parti del numero di versione (ad esempio, "v1.0.1529").</span><span class="sxs-lookup"><span data-stu-id="d3a18-109">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="d3a18-110">Alcune versioni di CLR vengono installate con un'istruzione dei criteri che specifica la compatibilità con le versioni precedenti di CLR.</span><span class="sxs-lookup"><span data-stu-id="d3a18-110">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="d3a18-111">Per impostazione predefinita, lo `pwszVersion` shim di avvio valuta rispetto alle istruzioni dei criteri e carica la versione più recente del runtime compatibile con la versione richiesta.</span><span class="sxs-lookup"><span data-stu-id="d3a18-111">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="d3a18-112">Un host può forzare lo shim a ignorare `pwszVersion` la valutazione dei `STARTUP_LOADER_SAFEMODE` criteri `flags` e caricare la versione esatta specificata in passando un valore di per il parametro, come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="d3a18-112">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of  `STARTUP_LOADER_SAFEMODE` for the `flags` parameter, as described below.</span></span>  
  
 <span data-ttu-id="d3a18-113">Se il chiamante `pwszVersion`specifica null per , viene caricata la versione più recente del runtime.</span><span class="sxs-lookup"><span data-stu-id="d3a18-113">If the caller specifies null for `pwszVersion`, the latest version of the runtime is loaded.</span></span> <span data-ttu-id="d3a18-114">Il passaggio di null non fornisce all'host alcun controllo sulla versione del runtime caricata.</span><span class="sxs-lookup"><span data-stu-id="d3a18-114">Passing null gives the host no control over which version of the runtime is loaded.</span></span> <span data-ttu-id="d3a18-115">Anche se questo approccio può essere appropriato in alcuni scenari, è consigliabile che l'host fornisse una versione specifica da caricare.</span><span class="sxs-lookup"><span data-stu-id="d3a18-115">Although this approach may be appropriate in some scenarios, it is strongly recommended that the host supply a specific version to load.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="d3a18-116">[in] Stringa che specifica se caricare il server o la build della workstation di CLR.</span><span class="sxs-lookup"><span data-stu-id="d3a18-116">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="d3a18-117">I valori validi sono `svr` e `wks`.</span><span class="sxs-lookup"><span data-stu-id="d3a18-117">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="d3a18-118">La build server è ottimizzata per sfruttare più processori per le operazioni di Garbage Collection e la build workstation è ottimizzata per le applicazioni client in esecuzione su un computer a processore singolo.</span><span class="sxs-lookup"><span data-stu-id="d3a18-118">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="d3a18-119">Se `pwszBuildFlavor` è impostato su null, viene caricata la build della workstation.</span><span class="sxs-lookup"><span data-stu-id="d3a18-119">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="d3a18-120">Quando viene eseguita su un computer a processore singolo, la build della workstation viene sempre caricata, anche se `pwszBuildFlavor` è impostata su `svr`.</span><span class="sxs-lookup"><span data-stu-id="d3a18-120">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="d3a18-121">Tuttavia, `pwszBuildFlavor` se `svr` è impostata su e viene specificata `flags` l'operazione di Garbage Collection simultanea (vedere la descrizione del parametro), viene caricata la compilazione del server.</span><span class="sxs-lookup"><span data-stu-id="d3a18-121">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `flags` parameter), the server build is loaded.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="d3a18-122">[in] La `CLSID` della coclasse che implementa il [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) o [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d3a18-122">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="d3a18-123">I valori supportati sono CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="d3a18-123">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="d3a18-124">[in] L'interfaccia `IID` richiesta `rclsid`da .</span><span class="sxs-lookup"><span data-stu-id="d3a18-124">[in] The `IID` of the requested interface from `rclsid`.</span></span> <span data-ttu-id="d3a18-125">I valori supportati sono IID_ICorRuntimeHost o IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="d3a18-125">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="d3a18-126">[fuori] Puntatore a interfaccia `riid`restituito a .</span><span class="sxs-lookup"><span data-stu-id="d3a18-126">[out] The returned interface pointer to `riid`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3a18-127">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d3a18-127">Remarks</span></span>  
 <span data-ttu-id="d3a18-128">Se `pwszVersion` specifica una versione di runtime `CorBindToRuntimeEx` che non esiste, restituisce un valore HRESULT di CLR_E_SHIM_RUNTIMELOAD.</span><span class="sxs-lookup"><span data-stu-id="d3a18-128">If `pwszVersion` specifies a runtime version that does not exist, `CorBindToRuntimeEx` returns an HRESULT value of CLR_E_SHIM_RUNTIMELOAD.</span></span>  
  
## <a name="execution-context-and-flow-of-windows-identity"></a><span data-ttu-id="d3a18-129">Contesto di esecuzione e flusso dell'identità di WindowsExecution Context and Flow of Windows Identity</span><span class="sxs-lookup"><span data-stu-id="d3a18-129">Execution Context and Flow of Windows Identity</span></span>  
 <span data-ttu-id="d3a18-130">Nella versione 1 di <xref:System.Security.Principal.WindowsIdentity> CLR, l'oggetto non passa attraverso punti asincroni, ad esempio nuovi thread, pool di thread o callback del timer.</span><span class="sxs-lookup"><span data-stu-id="d3a18-130">In version 1 of the CLR, the <xref:System.Security.Principal.WindowsIdentity> object does not flow across asynchronous points such as new threads, thread pools, or timer callbacks.</span></span> <span data-ttu-id="d3a18-131">Nella versione 2.0 di <xref:System.Threading.ExecutionContext> CLR, un oggetto esegue il wrapping di alcune informazioni sul thread attualmente in esecuzione e lo scorre attraverso qualsiasi punto asincrono, ma non attraverso i limiti del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="d3a18-131">In version 2.0 of the CLR, an <xref:System.Threading.ExecutionContext> object wraps some information about the currently executing thread and flows it across any asynchronous point, but not across application domain boundaries.</span></span> <span data-ttu-id="d3a18-132">Analogamente, <xref:System.Security.Principal.WindowsIdentity> l'oggetto scorre anche attraverso qualsiasi punto asincrono.</span><span class="sxs-lookup"><span data-stu-id="d3a18-132">Similarly, the <xref:System.Security.Principal.WindowsIdentity> object also flows across any asynchronous point.</span></span> <span data-ttu-id="d3a18-133">Pertanto, la rappresentazione corrente nel thread, se presente, scorre troppo.</span><span class="sxs-lookup"><span data-stu-id="d3a18-133">Therefore, the current impersonation on the thread, if any, flows too.</span></span>  
  
 <span data-ttu-id="d3a18-134">È possibile modificare il flusso in due modi:</span><span class="sxs-lookup"><span data-stu-id="d3a18-134">You can alter the flow in two ways:</span></span>  
  
1. <span data-ttu-id="d3a18-135">Modificando le <xref:System.Threading.ExecutionContext> impostazioni per sopprimere il flusso <xref:System.Threading.ExecutionContext.SuppressFlow%2A>in <xref:System.Security.SecurityContext.SuppressFlow%2A>base <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> al thread (vedere i metodi , e ).</span><span class="sxs-lookup"><span data-stu-id="d3a18-135">By modifying the <xref:System.Threading.ExecutionContext> settings to suppress the flow on a per-thread basis (see the <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, and <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> methods).</span></span>  
  
2. <span data-ttu-id="d3a18-136">Modificando la modalità predefinita del processo alla <xref:System.Security.Principal.WindowsIdentity> modalità di compatibilità della versione 1, in cui l'oggetto non passa attraverso alcun punto asincrono, indipendentemente dalle <xref:System.Threading.ExecutionContext> impostazioni nel thread corrente.</span><span class="sxs-lookup"><span data-stu-id="d3a18-136">By changing the process default mode to the version 1 compatibility mode, where the <xref:System.Security.Principal.WindowsIdentity> object does not flow across any asynchronous point, regardless of the <xref:System.Threading.ExecutionContext> settings on the current thread.</span></span> <span data-ttu-id="d3a18-137">La modalità di modifica della modalità predefinita dipende dall'utilizzo di un eseguibile gestito o di un'interfaccia di hosting non gestita per caricare CLR:</span><span class="sxs-lookup"><span data-stu-id="d3a18-137">How you change the default mode depends on whether you use a managed executable or an unmanaged hosting interface to load the CLR:</span></span>  
  
    1. <span data-ttu-id="d3a18-138">Per gli eseguibili gestiti, è necessario impostare l'attributo `enabled` dell'elemento `true` [ \<legacyImpersonationPolicy>](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) su .</span><span class="sxs-lookup"><span data-stu-id="d3a18-138">For managed executables, you must set the `enabled` attribute of the [\<legacyImpersonationPolicy>](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) element to `true`.</span></span>  
  
    2. <span data-ttu-id="d3a18-139">Per le interfacce di `STARTUP_LEGACY_IMPERSONATION` hosting non `flags` gestite, `CorBindToRuntimeEx` impostare il flag nel parametro quando si chiama la funzione.</span><span class="sxs-lookup"><span data-stu-id="d3a18-139">For unmanaged hosting interfaces, set the `STARTUP_LEGACY_IMPERSONATION` flag in the `flags` parameter when calling the `CorBindToRuntimeEx` function.</span></span>  
  
     <span data-ttu-id="d3a18-140">La modalità di compatibilità versione 1 si applica all'intero processo e a tutti i domini applicazione del processo.</span><span class="sxs-lookup"><span data-stu-id="d3a18-140">The version 1 compatibility mode applies to the entire process and to all the application domains in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3a18-141">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d3a18-141">Remarks</span></span>  
 <span data-ttu-id="d3a18-142">[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) `CorBindToRuntime` ed eseguire la stessa `CorBindToRuntimeEx` operazione, ma la funzione consente di impostare i flag per specificare il comportamento di CLR.</span><span class="sxs-lookup"><span data-stu-id="d3a18-142">[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and `CorBindToRuntime` perform the same operation, but the `CorBindToRuntimeEx` function allows you to set flags to specify the behavior of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3a18-143">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d3a18-143">Requirements</span></span>  
 <span data-ttu-id="d3a18-144">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3a18-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3a18-145">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d3a18-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d3a18-146">**Biblioteca:** Mscoree</span><span class="sxs-lookup"><span data-stu-id="d3a18-146">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d3a18-147">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3a18-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3a18-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3a18-148">See also</span></span>

- [<span data-ttu-id="d3a18-149">Funzione CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="d3a18-149">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="d3a18-150">Funzione CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="d3a18-150">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="d3a18-151">Funzione CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="d3a18-151">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="d3a18-152">Funzione CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="d3a18-152">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [<span data-ttu-id="d3a18-153">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="d3a18-153">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="d3a18-154">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="d3a18-154">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

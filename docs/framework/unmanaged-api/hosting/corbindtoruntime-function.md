---
title: Funzione CorBindToRuntime
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6e6ce976961eedaa58ad265a133c15b2f27a8985
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="corbindtoruntime-function"></a><span data-ttu-id="134bf-102">Funzione CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="134bf-102">CorBindToRuntime Function</span></span>
<span data-ttu-id="134bf-103">Consente l'host non gestiti di caricare common language runtime (CLR) in un processo.</span><span class="sxs-lookup"><span data-stu-id="134bf-103">Enables unmanaged hosts to load the common language runtime (CLR) into a process.</span></span>  
  
 <span data-ttu-id="134bf-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="134bf-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="134bf-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="134bf-105">Syntax</span></span>  
  
```  
HRESULT CorBindToRuntime (  
    [in]  LPCWSTR     pwszVersion,   
    [in]  LPCWSTR     pwszBuildFlavor,   
    [in]  REFCLSID    rclsid,   
    [in]  REFIID      riid,   
    [out] LPVOID FAR  *ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="134bf-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="134bf-106">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="134bf-107">[in] Stringa che descrive la versione di CLR a cui si desidera caricare.</span><span class="sxs-lookup"><span data-stu-id="134bf-107">[in] A string describing the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="134bf-108">Un numero di versione di .NET Framework è costituito da quattro parti separate da punti: *revisione*.</span><span class="sxs-lookup"><span data-stu-id="134bf-108">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="134bf-109">La stringa passata come `pwszVersion` deve iniziare con il carattere "v" seguito dalle prime tre parti del numero di versione (ad esempio, "v 1.0.1529").</span><span class="sxs-lookup"><span data-stu-id="134bf-109">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="134bf-110">Alcune versioni di Common Language Runtime vengono installati con un'istruzione di criteri che specifica la compatibilità con le versioni precedenti di CLR.</span><span class="sxs-lookup"><span data-stu-id="134bf-110">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="134bf-111">Per impostazione predefinita, valuta lo shim di avvio `pwszVersion` contro istruzioni dei criteri e carica la versione più recente del runtime che è compatibile con la versione richiesta.</span><span class="sxs-lookup"><span data-stu-id="134bf-111">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="134bf-112">Un host può imporre allo shim di ignorare la valutazione dei criteri e caricare l'esatta versione specificata `pwszVersion` passando un valore di `STARTUP_LOADER_SAFEMODE` per il `flags` parametro, come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="134bf-112">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of  `STARTUP_LOADER_SAFEMODE` for the `flags` parameter, as described below.</span></span>  
  
 <span data-ttu-id="134bf-113">Se il chiamante specifica null per `pwszVersion`, viene caricata la versione più recente del runtime.</span><span class="sxs-lookup"><span data-stu-id="134bf-113">If the caller specifies null for `pwszVersion`, the latest version of the runtime is loaded.</span></span> <span data-ttu-id="134bf-114">Passaggio di null non consente all'host di alcun controllo sulla quale versione del runtime viene caricata.</span><span class="sxs-lookup"><span data-stu-id="134bf-114">Passing null gives the host no control over which version of the runtime is loaded.</span></span> <span data-ttu-id="134bf-115">Sebbene questo approccio può risultare appropriato in alcuni scenari, è consigliabile che l'host fornisca una specifica versione da caricare.</span><span class="sxs-lookup"><span data-stu-id="134bf-115">Although this approach may be appropriate in some scenarios, it is strongly recommended that the host supply a specific version to load.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="134bf-116">[in] Stringa che specifica se caricare il server o la compilazione di workstation di CLR.</span><span class="sxs-lookup"><span data-stu-id="134bf-116">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="134bf-117">I valori validi sono `svr` e `wks`.</span><span class="sxs-lookup"><span data-stu-id="134bf-117">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="134bf-118">La compilazione di server è ottimizzata per sfruttare i vantaggi di più processori per operazioni di garbage collection e la compilazione di workstation è ottimizzata per le applicazioni client eseguite in un computer a processore singolo.</span><span class="sxs-lookup"><span data-stu-id="134bf-118">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="134bf-119">Se `pwszBuildFlavor` è impostato su null, viene caricata la build per workstation.</span><span class="sxs-lookup"><span data-stu-id="134bf-119">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="134bf-120">Quando si esegue in un computer a processore singolo, la compilazione della workstation viene sempre caricata, anche se `pwszBuildFlavor` è impostato su `svr`.</span><span class="sxs-lookup"><span data-stu-id="134bf-120">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="134bf-121">Tuttavia, se `pwszBuildFlavor` è impostato su `svr` e garbage collection simultanea è specificata (vedere la descrizione del `flags` parametro), verrà caricata la build del server.</span><span class="sxs-lookup"><span data-stu-id="134bf-121">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `flags` parameter), the server build is loaded.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="134bf-122">[in] Il `CLSID` della coclasse che implementa il [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) o [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="134bf-122">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="134bf-123">Valori supportati sono CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="134bf-123">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="134bf-124">[in] Il `IID` dell'interfaccia richiesta da `rclsid`.</span><span class="sxs-lookup"><span data-stu-id="134bf-124">[in] The `IID` of the requested interface from `rclsid`.</span></span> <span data-ttu-id="134bf-125">Valori supportati sono IID_ICorRuntimeHost o IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="134bf-125">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="134bf-126">[out] Il puntatore a interfaccia restituito `riid`.</span><span class="sxs-lookup"><span data-stu-id="134bf-126">[out] The returned interface pointer to `riid`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="134bf-127">Note</span><span class="sxs-lookup"><span data-stu-id="134bf-127">Remarks</span></span>  
 <span data-ttu-id="134bf-128">Se `pwszVersion` specifica una versione di runtime che non esiste, `CorBindToRuntimeEx` restituisce un valore HRESULT di CLR_E_SHIM_RUNTIMELOAD.</span><span class="sxs-lookup"><span data-stu-id="134bf-128">If `pwszVersion` specifies a runtime version that does not exist, `CorBindToRuntimeEx` returns an HRESULT value of CLR_E_SHIM_RUNTIMELOAD.</span></span>  
  
## <a name="execution-context-and-flow-of-windows-identity"></a><span data-ttu-id="134bf-129">Contesto di esecuzione e il flusso dell'identità di Windows</span><span class="sxs-lookup"><span data-stu-id="134bf-129">Execution Context and Flow of Windows Identity</span></span>  
 <span data-ttu-id="134bf-130">Nella versione 1 di CLR, la <xref:System.Security.Principal.WindowsIdentity> oggetto non passa attraverso punti asincroni, ad esempio nuovi thread, pool di thread o i callback del timer.</span><span class="sxs-lookup"><span data-stu-id="134bf-130">In version 1 of the CLR, the <xref:System.Security.Principal.WindowsIdentity> object does not flow across asynchronous points such as new threads, thread pools, or timer callbacks.</span></span> <span data-ttu-id="134bf-131">Nella versione 2.0 di CLR, un <xref:System.Threading.ExecutionContext> oggetto esegue il wrapping di alcune informazioni sul thread attualmente in esecuzione e ne effettua tra punti asincroni qualsiasi, ma non attraverso i limiti del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="134bf-131">In version 2.0 of the CLR, an <xref:System.Threading.ExecutionContext> object wraps some information about the currently executing thread and flows it across any asynchronous point, but not across application domain boundaries.</span></span> <span data-ttu-id="134bf-132">Analogamente, il <xref:System.Security.Principal.WindowsIdentity> oggetto anche passa attraverso un punto qualsiasi asincrono.</span><span class="sxs-lookup"><span data-stu-id="134bf-132">Similarly, the <xref:System.Security.Principal.WindowsIdentity> object also flows across any asynchronous point.</span></span> <span data-ttu-id="134bf-133">Pertanto, la rappresentazione corrente nel thread, se presente, i flussi troppo.</span><span class="sxs-lookup"><span data-stu-id="134bf-133">Therefore, the current impersonation on the thread, if any, flows too.</span></span>  
  
 <span data-ttu-id="134bf-134">È possibile modificare il flusso in due modi:</span><span class="sxs-lookup"><span data-stu-id="134bf-134">You can alter the flow in two ways:</span></span>  
  
1.  <span data-ttu-id="134bf-135">Modificando il <xref:System.Threading.ExecutionContext> le impostazioni per eliminare il flusso in base al thread (vedere il <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, e <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> metodi).</span><span class="sxs-lookup"><span data-stu-id="134bf-135">By modifying the <xref:System.Threading.ExecutionContext> settings to suppress the flow on a per-thread basis (see the <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, and <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> methods).</span></span>  
  
2.  <span data-ttu-id="134bf-136">Modificando la modalità predefinita di processo per la modalità di compatibilità di versione 1, in cui il <xref:System.Security.Principal.WindowsIdentity> oggetto non passa attraverso punti asincroni qualsiasi, indipendentemente dal valore di <xref:System.Threading.ExecutionContext> impostazioni sul thread corrente.</span><span class="sxs-lookup"><span data-stu-id="134bf-136">By changing the process default mode to the version 1 compatibility mode, where the <xref:System.Security.Principal.WindowsIdentity> object does not flow across any asynchronous point, regardless of the <xref:System.Threading.ExecutionContext> settings on the current thread.</span></span> <span data-ttu-id="134bf-137">Cambiare la modalità predefinita varia a seconda se si utilizza un file eseguibile gestito o in un'interfaccia di hosting non gestita per caricare Common Language Runtime:</span><span class="sxs-lookup"><span data-stu-id="134bf-137">How you change the default mode depends on whether you use a managed executable or an unmanaged hosting interface to load the CLR:</span></span>  
  
    1.  <span data-ttu-id="134bf-138">Per gli eseguibili gestiti, è necessario impostare il `enabled` attributo del [ \<legacyImpersonationPolicy >](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) elemento `true`.</span><span class="sxs-lookup"><span data-stu-id="134bf-138">For managed executables, you must set the `enabled` attribute of the [\<legacyImpersonationPolicy>](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) element to `true`.</span></span>  
  
    2.  <span data-ttu-id="134bf-139">Per non gestita di interfacce di hosting, impostare il `STARTUP_LEGACY_IMPERSONATION` flag nel `flags` parametro quando si chiama il `CorBindToRuntimeEx` (funzione).</span><span class="sxs-lookup"><span data-stu-id="134bf-139">For unmanaged hosting interfaces, set the `STARTUP_LEGACY_IMPERSONATION` flag in the `flags` parameter when calling the `CorBindToRuntimeEx` function.</span></span>  
  
     <span data-ttu-id="134bf-140">La modalità di compatibilità della versione 1 si applica all'intero processo e tutti i domini applicazione nel processo.</span><span class="sxs-lookup"><span data-stu-id="134bf-140">The version 1 compatibility mode applies to the entire process and to all the application domains in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="134bf-141">Note</span><span class="sxs-lookup"><span data-stu-id="134bf-141">Remarks</span></span>  
 <span data-ttu-id="134bf-142">[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) e `CorBindToRuntime` eseguono la stessa operazione, ma la `CorBindToRuntimeEx` funzione consente di impostare flag per specificare il comportamento di CLR.</span><span class="sxs-lookup"><span data-stu-id="134bf-142">[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and `CorBindToRuntime` perform the same operation, but the `CorBindToRuntimeEx` function allows you to set flags to specify the behavior of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="134bf-143">Requisiti</span><span class="sxs-lookup"><span data-stu-id="134bf-143">Requirements</span></span>  
 <span data-ttu-id="134bf-144">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="134bf-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="134bf-145">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="134bf-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="134bf-146">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="134bf-146">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="134bf-147">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="134bf-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="134bf-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="134bf-148">See Also</span></span>  
 [<span data-ttu-id="134bf-149">Funzione CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="134bf-149">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 [<span data-ttu-id="134bf-150">Funzione CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="134bf-150">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 [<span data-ttu-id="134bf-151">Funzione CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="134bf-151">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [<span data-ttu-id="134bf-152">Funzione CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="134bf-152">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 [<span data-ttu-id="134bf-153">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="134bf-153">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [<span data-ttu-id="134bf-154">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="134bf-154">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

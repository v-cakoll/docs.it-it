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
ms.openlocfilehash: 52594c36c54c74941371f9950fbc6fb543b86de0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493552"
---
# <a name="corbindtoruntime-function"></a><span data-ttu-id="61496-102">Funzione CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="61496-102">CorBindToRuntime Function</span></span>
<span data-ttu-id="61496-103">Consente agli host non gestiti di caricare il Common Language Runtime (CLR) in un processo.</span><span class="sxs-lookup"><span data-stu-id="61496-103">Enables unmanaged hosts to load the common language runtime (CLR) into a process.</span></span>  
  
 <span data-ttu-id="61496-104">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="61496-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61496-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="61496-105">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToRuntime (  
    [in]  LPCWSTR     pwszVersion,
    [in]  LPCWSTR     pwszBuildFlavor,
    [in]  REFCLSID    rclsid,
    [in]  REFIID      riid,
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61496-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="61496-106">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="61496-107">in Stringa che descrive la versione di CLR che si desidera caricare.</span><span class="sxs-lookup"><span data-stu-id="61496-107">[in] A string describing the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="61496-108">Un numero di versione nel .NET Framework è costituito da quattro parti separate da punti: *Major. minor. Build. Revision*.</span><span class="sxs-lookup"><span data-stu-id="61496-108">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="61496-109">La stringa passata come `pwszVersion` deve iniziare con il carattere "v" seguito dalle prime tre parti del numero di versione (ad esempio, "v 1.0.1529").</span><span class="sxs-lookup"><span data-stu-id="61496-109">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="61496-110">Alcune versioni di CLR vengono installate con un'istruzione di criteri che specifica la compatibilità con le versioni precedenti di CLR.</span><span class="sxs-lookup"><span data-stu-id="61496-110">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="61496-111">Per impostazione predefinita, lo shim di avvio valuta le `pwszVersion` istruzioni dei criteri e carica la versione più recente del runtime compatibile con la versione richiesta.</span><span class="sxs-lookup"><span data-stu-id="61496-111">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="61496-112">Un host può forzare lo shim a ignorare la valutazione dei criteri e caricare la versione esatta specificata in `pwszVersion` passando un valore `STARTUP_LOADER_SAFEMODE` per il `flags` parametro, come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="61496-112">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of  `STARTUP_LOADER_SAFEMODE` for the `flags` parameter, as described below.</span></span>  
  
 <span data-ttu-id="61496-113">Se il chiamante specifica null per `pwszVersion` , viene caricata la versione più recente del runtime.</span><span class="sxs-lookup"><span data-stu-id="61496-113">If the caller specifies null for `pwszVersion`, the latest version of the runtime is loaded.</span></span> <span data-ttu-id="61496-114">Il passaggio di valori null consente all'host di non controllare la versione del runtime caricata.</span><span class="sxs-lookup"><span data-stu-id="61496-114">Passing null gives the host no control over which version of the runtime is loaded.</span></span> <span data-ttu-id="61496-115">Sebbene questo approccio possa essere appropriato in alcuni scenari, si consiglia vivamente all'host di fornire una versione specifica da caricare.</span><span class="sxs-lookup"><span data-stu-id="61496-115">Although this approach may be appropriate in some scenarios, it is strongly recommended that the host supply a specific version to load.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="61496-116">in Stringa che specifica se caricare il server o la build della workstation di CLR.</span><span class="sxs-lookup"><span data-stu-id="61496-116">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="61496-117">I valori validi sono `svr` e `wks`.</span><span class="sxs-lookup"><span data-stu-id="61496-117">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="61496-118">La compilazione server è ottimizzata per sfruttare i vantaggi di più processori per le operazioni di Garbage Collection e la compilazione della workstation è ottimizzata per le applicazioni client in esecuzione su un computer a processore singolo.</span><span class="sxs-lookup"><span data-stu-id="61496-118">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="61496-119">Se `pwszBuildFlavor` è impostato su null, viene caricata la compilazione della workstation.</span><span class="sxs-lookup"><span data-stu-id="61496-119">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="61496-120">Quando è in esecuzione in un computer a processore singolo, la compilazione della workstation viene sempre caricata, anche se `pwszBuildFlavor` è impostato su `svr` .</span><span class="sxs-lookup"><span data-stu-id="61496-120">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="61496-121">Tuttavia, se `pwszBuildFlavor` è impostato su `svr` e viene specificato Garbage Collection simultaneo (vedere la descrizione del `flags` parametro), viene caricata la compilazione del server.</span><span class="sxs-lookup"><span data-stu-id="61496-121">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `flags` parameter), the server build is loaded.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="61496-122">in `CLSID`Della coclasse che implementa l'interfaccia [ICorRuntimeHost](icorruntimehost-interface.md) o [ICLRRuntimeHost](iclrruntimehost-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="61496-122">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](icorruntimehost-interface.md) or the [ICLRRuntimeHost](iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="61496-123">I valori supportati sono CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="61496-123">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="61496-124">in `IID`Dell'interfaccia richiesta da `rclsid` .</span><span class="sxs-lookup"><span data-stu-id="61496-124">[in] The `IID` of the requested interface from `rclsid`.</span></span> <span data-ttu-id="61496-125">I valori supportati sono IID_ICorRuntimeHost o IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="61496-125">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="61496-126">out Puntatore a interfaccia restituito a `riid` .</span><span class="sxs-lookup"><span data-stu-id="61496-126">[out] The returned interface pointer to `riid`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61496-127">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="61496-127">Remarks</span></span>  
 <span data-ttu-id="61496-128">Se `pwszVersion` specifica una versione runtime che non esiste, `CorBindToRuntimeEx` restituisce un valore HRESULT pari a CLR_E_SHIM_RUNTIMELOAD.</span><span class="sxs-lookup"><span data-stu-id="61496-128">If `pwszVersion` specifies a runtime version that does not exist, `CorBindToRuntimeEx` returns an HRESULT value of CLR_E_SHIM_RUNTIMELOAD.</span></span>  
  
## <a name="execution-context-and-flow-of-windows-identity"></a><span data-ttu-id="61496-129">Contesto di esecuzione e flusso di identità Windows</span><span class="sxs-lookup"><span data-stu-id="61496-129">Execution Context and Flow of Windows Identity</span></span>  
 <span data-ttu-id="61496-130">Nella versione 1 di CLR, l' <xref:System.Security.Principal.WindowsIdentity> oggetto non scorre tra punti asincroni, ad esempio nuovi thread, pool di thread o callback del timer.</span><span class="sxs-lookup"><span data-stu-id="61496-130">In version 1 of the CLR, the <xref:System.Security.Principal.WindowsIdentity> object does not flow across asynchronous points such as new threads, thread pools, or timer callbacks.</span></span> <span data-ttu-id="61496-131">Nella versione 2,0 di CLR, un <xref:System.Threading.ExecutionContext> oggetto esegue il wrapping di alcune informazioni sul thread attualmente in esecuzione e lo trasmette attraverso qualsiasi punto asincrono, ma non tra i limiti del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="61496-131">In version 2.0 of the CLR, an <xref:System.Threading.ExecutionContext> object wraps some information about the currently executing thread and flows it across any asynchronous point, but not across application domain boundaries.</span></span> <span data-ttu-id="61496-132">Analogamente, l' <xref:System.Security.Principal.WindowsIdentity> oggetto fluisce anche su qualsiasi punto asincrono.</span><span class="sxs-lookup"><span data-stu-id="61496-132">Similarly, the <xref:System.Security.Principal.WindowsIdentity> object also flows across any asynchronous point.</span></span> <span data-ttu-id="61496-133">Quindi, la rappresentazione corrente sul thread, se presente, scorre anche.</span><span class="sxs-lookup"><span data-stu-id="61496-133">Therefore, the current impersonation on the thread, if any, flows too.</span></span>  
  
 <span data-ttu-id="61496-134">È possibile modificare il flusso in due modi:</span><span class="sxs-lookup"><span data-stu-id="61496-134">You can alter the flow in two ways:</span></span>  
  
1. <span data-ttu-id="61496-135">Modificando le <xref:System.Threading.ExecutionContext> impostazioni per escludere il flusso per ogni singolo thread (vedere i <xref:System.Threading.ExecutionContext.SuppressFlow%2A> metodi, <xref:System.Security.SecurityContext.SuppressFlow%2A> e <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> ).</span><span class="sxs-lookup"><span data-stu-id="61496-135">By modifying the <xref:System.Threading.ExecutionContext> settings to suppress the flow on a per-thread basis (see the <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, and <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> methods).</span></span>  
  
2. <span data-ttu-id="61496-136">Modificando la modalità predefinita del processo con la modalità di compatibilità versione 1, in cui l' <xref:System.Security.Principal.WindowsIdentity> oggetto non viene propagato in alcun punto asincrono, indipendentemente dalle <xref:System.Threading.ExecutionContext> impostazioni nel thread corrente.</span><span class="sxs-lookup"><span data-stu-id="61496-136">By changing the process default mode to the version 1 compatibility mode, where the <xref:System.Security.Principal.WindowsIdentity> object does not flow across any asynchronous point, regardless of the <xref:System.Threading.ExecutionContext> settings on the current thread.</span></span> <span data-ttu-id="61496-137">La modalità di modifica della modalità predefinita varia a seconda che si usi un eseguibile gestito o un'interfaccia di hosting non gestita per caricare il CLR:</span><span class="sxs-lookup"><span data-stu-id="61496-137">How you change the default mode depends on whether you use a managed executable or an unmanaged hosting interface to load the CLR:</span></span>  
  
    1. <span data-ttu-id="61496-138">Per i file eseguibili gestiti, è necessario impostare l' `enabled` attributo dell' [\<legacyImpersonationPolicy>](../../configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) elemento su `true` .</span><span class="sxs-lookup"><span data-stu-id="61496-138">For managed executables, you must set the `enabled` attribute of the [\<legacyImpersonationPolicy>](../../configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) element to `true`.</span></span>  
  
    2. <span data-ttu-id="61496-139">Per le interfacce di hosting non gestite, impostare il `STARTUP_LEGACY_IMPERSONATION` flag nel `flags` parametro quando si chiama la `CorBindToRuntimeEx` funzione.</span><span class="sxs-lookup"><span data-stu-id="61496-139">For unmanaged hosting interfaces, set the `STARTUP_LEGACY_IMPERSONATION` flag in the `flags` parameter when calling the `CorBindToRuntimeEx` function.</span></span>  
  
     <span data-ttu-id="61496-140">La modalità di compatibilità versione 1 si applica all'intero processo e a tutti i domini applicazione nel processo.</span><span class="sxs-lookup"><span data-stu-id="61496-140">The version 1 compatibility mode applies to the entire process and to all the application domains in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61496-141">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="61496-141">Remarks</span></span>  
 <span data-ttu-id="61496-142">[CorBindToRuntimeEx](corbindtoruntimeex-function.md) ed `CorBindToRuntime` eseguono la stessa operazione, ma la `CorBindToRuntimeEx` funzione consente di impostare i flag per specificare il comportamento di CLR.</span><span class="sxs-lookup"><span data-stu-id="61496-142">[CorBindToRuntimeEx](corbindtoruntimeex-function.md) and `CorBindToRuntime` perform the same operation, but the `CorBindToRuntimeEx` function allows you to set flags to specify the behavior of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61496-143">Requisiti</span><span class="sxs-lookup"><span data-stu-id="61496-143">Requirements</span></span>  
 <span data-ttu-id="61496-144">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61496-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61496-145">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="61496-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="61496-146">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="61496-146">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="61496-147">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61496-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61496-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61496-148">See also</span></span>

- [<span data-ttu-id="61496-149">Funzione CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="61496-149">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)
- [<span data-ttu-id="61496-150">Funzione CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="61496-150">CorBindToRuntimeByCfg Function</span></span>](corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="61496-151">Funzione CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="61496-151">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="61496-152">Funzione CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="61496-152">CorBindToRuntimeHost Function</span></span>](corbindtoruntimehost-function.md)
- [<span data-ttu-id="61496-153">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="61496-153">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="61496-154">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="61496-154">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)

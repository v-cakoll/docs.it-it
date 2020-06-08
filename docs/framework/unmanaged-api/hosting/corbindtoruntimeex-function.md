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
ms.openlocfilehash: e66b63ffa4ed25e861cff6bd9eb6065f57ff807f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493500"
---
# <a name="corbindtoruntimeex-function"></a><span data-ttu-id="50584-102">Funzione CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="50584-102">CorBindToRuntimeEx Function</span></span>
<span data-ttu-id="50584-103">Consente agli host non gestiti di caricare il Common Language Runtime (CLR) in un processo.</span><span class="sxs-lookup"><span data-stu-id="50584-103">Enables unmanaged hosts to load the common language runtime (CLR) into a process.</span></span> <span data-ttu-id="50584-104">Le funzioni [CorBindToRuntime](corbindtoruntime-function.md) e `CorBindToRuntimeEx` eseguono la stessa operazione, ma la `CorBindToRuntimeEx` funzione consente di impostare i flag per specificare il comportamento di CLR.</span><span class="sxs-lookup"><span data-stu-id="50584-104">The [CorBindToRuntime](corbindtoruntime-function.md) and `CorBindToRuntimeEx` functions perform the same operation, but the `CorBindToRuntimeEx` function allows you to set flags to specify the behavior of the CLR.</span></span>  
  
 <span data-ttu-id="50584-105">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="50584-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
 <span data-ttu-id="50584-106">Questa funzione accetta un set di parametri che consentono a un host di eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="50584-106">This function takes a set of parameters that allow a host to do the following:</span></span>  
  
- <span data-ttu-id="50584-107">Consente di specificare la versione del runtime da caricare.</span><span class="sxs-lookup"><span data-stu-id="50584-107">Specify the version of the runtime that will be loaded.</span></span>  
  
- <span data-ttu-id="50584-108">Indica se è necessario caricare la build del server o della workstation.</span><span class="sxs-lookup"><span data-stu-id="50584-108">Indicate whether the server or workstation build should be loaded.</span></span>  
  
- <span data-ttu-id="50584-109">Controllare se viene eseguita la Garbage Collection simultanea Garbage Collection o non simultanea.</span><span class="sxs-lookup"><span data-stu-id="50584-109">Control whether concurrent garbage collection or non-concurrent garbage collection is done.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="50584-110">La Garbage Collection simultanea non è supportata nelle applicazioni che eseguono l'emulatore WOW64 x86 nei sistemi a 64 bit che implementano l'architettura Intel Itanium (denominata in precedenza IA-64).</span><span class="sxs-lookup"><span data-stu-id="50584-110">Concurrent garbage collection is not supported in applications running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="50584-111">Per ulteriori informazioni sull'utilizzo di WOW64 in sistemi Windows a 64 bit, vedere [esecuzione di applicazioni a 32 bit](/windows/desktop/WinProg64/running-32-bit-applications).</span><span class="sxs-lookup"><span data-stu-id="50584-111">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](/windows/desktop/WinProg64/running-32-bit-applications).</span></span>  
  
- <span data-ttu-id="50584-112">Controllare se gli assembly vengono caricati come indipendenti dal dominio.</span><span class="sxs-lookup"><span data-stu-id="50584-112">Control whether assemblies are loaded as domain-neutral.</span></span>  
  
- <span data-ttu-id="50584-113">Ottenere un puntatore a interfaccia a un [ICorRuntimeHost](icorruntimehost-interface.md) che può essere utilizzato per impostare opzioni aggiuntive per la configurazione di un'istanza di CLR prima che venga avviata.</span><span class="sxs-lookup"><span data-stu-id="50584-113">Obtain an interface pointer to an [ICorRuntimeHost](icorruntimehost-interface.md) that can be used to set additional options for configuring an instance of the CLR before it is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50584-114">Sintassi</span><span class="sxs-lookup"><span data-stu-id="50584-114">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="50584-115">Parametri</span><span class="sxs-lookup"><span data-stu-id="50584-115">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="50584-116">in Stringa che descrive la versione di CLR che si desidera caricare.</span><span class="sxs-lookup"><span data-stu-id="50584-116">[in] A string describing the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="50584-117">Un numero di versione nel .NET Framework è costituito da quattro parti separate da punti: *Major. minor. Build. Revision*.</span><span class="sxs-lookup"><span data-stu-id="50584-117">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="50584-118">La stringa passata come `pwszVersion` deve iniziare con il carattere "v" seguito dalle prime tre parti del numero di versione (ad esempio, "v 1.0.1529").</span><span class="sxs-lookup"><span data-stu-id="50584-118">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="50584-119">Alcune versioni di CLR vengono installate con un'istruzione di criteri che specifica la compatibilità con le versioni precedenti di CLR.</span><span class="sxs-lookup"><span data-stu-id="50584-119">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="50584-120">Per impostazione predefinita, lo shim di avvio valuta le `pwszVersion` istruzioni dei criteri e carica la versione più recente del runtime compatibile con la versione richiesta.</span><span class="sxs-lookup"><span data-stu-id="50584-120">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="50584-121">Un host può forzare lo shim a ignorare la valutazione dei criteri e caricare la versione esatta specificata in `pwszVersion` passando un valore `STARTUP_LOADER_SAFEMODE` per il `startupFlags` parametro, come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="50584-121">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of  `STARTUP_LOADER_SAFEMODE` for the `startupFlags` parameter, as described below.</span></span>  
  
 <span data-ttu-id="50584-122">Se il chiamante specifica null per `pwszVersion` , `CorBindToRuntimeEx` identifica il set di runtime installati i cui numeri di versione sono inferiori al runtime di .NET Framework 4 e carica la versione più recente del runtime da tale set.</span><span class="sxs-lookup"><span data-stu-id="50584-122">If the caller specifies null for `pwszVersion`, `CorBindToRuntimeEx` identifies the set of installed runtimes whose version numbers are lower than the .NET Framework 4 runtime, and loads the latest version of the runtime from that set.</span></span> <span data-ttu-id="50584-123">Non caricherà il .NET Framework 4 o versione successiva e avrà esito negativo se non è installata alcuna versione precedente.</span><span class="sxs-lookup"><span data-stu-id="50584-123">It won't load the .NET Framework 4 or later, and fails if no earlier version is installed.</span></span> <span data-ttu-id="50584-124">Si noti che il passaggio di valori null consente all'host di non controllare la versione del runtime caricata.</span><span class="sxs-lookup"><span data-stu-id="50584-124">Note that passing null gives the host no control over which version of the runtime is loaded.</span></span> <span data-ttu-id="50584-125">Sebbene questo approccio possa essere appropriato in alcuni scenari, si consiglia vivamente all'host di fornire una versione specifica da caricare.</span><span class="sxs-lookup"><span data-stu-id="50584-125">Although this approach may be appropriate in some scenarios, it is strongly recommended that the host supply a specific version to load.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="50584-126">in Stringa che specifica se caricare il server o la build della workstation di CLR.</span><span class="sxs-lookup"><span data-stu-id="50584-126">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="50584-127">I valori validi sono `svr` e `wks`.</span><span class="sxs-lookup"><span data-stu-id="50584-127">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="50584-128">La compilazione server è ottimizzata per sfruttare i vantaggi di più processori per le operazioni di Garbage Collection e la compilazione della workstation è ottimizzata per le applicazioni client in esecuzione su un computer a processore singolo.</span><span class="sxs-lookup"><span data-stu-id="50584-128">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="50584-129">Se `pwszBuildFlavor` è impostato su null, viene caricata la compilazione della workstation.</span><span class="sxs-lookup"><span data-stu-id="50584-129">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="50584-130">Quando è in esecuzione in un computer a processore singolo, la compilazione della workstation viene sempre caricata, anche se `pwszBuildFlavor` è impostato su `svr` .</span><span class="sxs-lookup"><span data-stu-id="50584-130">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="50584-131">Tuttavia, se `pwszBuildFlavor` è impostato su `svr` e viene specificato Garbage Collection simultaneo (vedere la descrizione del `startupFlags` parametro), viene caricata la compilazione del server.</span><span class="sxs-lookup"><span data-stu-id="50584-131">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `startupFlags` parameter), the server build is loaded.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="50584-132">in Combinazione di valori dell'enumerazione [STARTUP_FLAGS](startup-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="50584-132">[in] A combination of values of the [STARTUP_FLAGS](startup-flags-enumeration.md) enumeration.</span></span> <span data-ttu-id="50584-133">Questi flag controllano Garbage Collection simultanee, il codice indipendente dal dominio e il comportamento del `pwszVersion` parametro.</span><span class="sxs-lookup"><span data-stu-id="50584-133">These flags control concurrent garbage collection, domain-neutral code, and the behavior of the `pwszVersion` parameter.</span></span> <span data-ttu-id="50584-134">Il valore predefinito è Single Domain se non è impostato alcun flag.</span><span class="sxs-lookup"><span data-stu-id="50584-134">The default is single domain if no flag is set.</span></span> <span data-ttu-id="50584-135">I valori seguenti sono validi:</span><span class="sxs-lookup"><span data-stu-id="50584-135">The following values are valid:</span></span>  
  
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
  
 <span data-ttu-id="50584-136">Per una descrizione di questi flag, vedere l'enumerazione [STARTUP_FLAGS](startup-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="50584-136">For descriptions of these flags, see the [STARTUP_FLAGS](startup-flags-enumeration.md) enumeration.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="50584-137">in `CLSID`Della coclasse che implementa l'interfaccia [ICorRuntimeHost](icorruntimehost-interface.md) o [ICLRRuntimeHost](iclrruntimehost-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="50584-137">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](icorruntimehost-interface.md) or the [ICLRRuntimeHost](iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="50584-138">I valori supportati sono CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="50584-138">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="50584-139">in `IID`Dell'interfaccia richiesta da `rclsid` .</span><span class="sxs-lookup"><span data-stu-id="50584-139">[in] The `IID` of the requested interface from `rclsid`.</span></span> <span data-ttu-id="50584-140">I valori supportati sono IID_ICorRuntimeHost o IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="50584-140">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="50584-141">out Puntatore a interfaccia restituito a `riid` .</span><span class="sxs-lookup"><span data-stu-id="50584-141">[out] The returned interface pointer to `riid`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50584-142">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="50584-142">Remarks</span></span>  
 <span data-ttu-id="50584-143">Se `pwszVersion` specifica una versione runtime che non esiste, `CorBindToRuntimeEx` restituisce un valore HRESULT pari a CLR_E_SHIM_RUNTIMELOAD.</span><span class="sxs-lookup"><span data-stu-id="50584-143">If `pwszVersion` specifies a runtime version that does not exist, `CorBindToRuntimeEx` returns an HRESULT value of CLR_E_SHIM_RUNTIMELOAD.</span></span>  
  
## <a name="execution-context-and-flow-of-windows-identity"></a><span data-ttu-id="50584-144">Contesto di esecuzione e flusso di identità Windows</span><span class="sxs-lookup"><span data-stu-id="50584-144">Execution Context and Flow of Windows Identity</span></span>  
 <span data-ttu-id="50584-145">Nella versione 1 di CLR, l' <xref:System.Security.Principal.WindowsIdentity> oggetto non scorre tra punti asincroni, ad esempio nuovi thread, pool di thread o callback del timer.</span><span class="sxs-lookup"><span data-stu-id="50584-145">In version 1 of the CLR, the <xref:System.Security.Principal.WindowsIdentity> object does not flow across asynchronous points such as new threads, thread pools, or timer callbacks.</span></span> <span data-ttu-id="50584-146">Nella versione 2,0 di CLR, un <xref:System.Threading.ExecutionContext> oggetto esegue il wrapping di alcune informazioni sul thread attualmente in esecuzione e lo trasmette attraverso qualsiasi punto asincrono, ma non tra i limiti del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="50584-146">In version 2.0 of the CLR, an <xref:System.Threading.ExecutionContext> object wraps some information about the currently executing thread and flows it across any asynchronous point, but not across application domain boundaries.</span></span> <span data-ttu-id="50584-147">Analogamente, l' <xref:System.Security.Principal.WindowsIdentity> oggetto fluisce anche su qualsiasi punto asincrono.</span><span class="sxs-lookup"><span data-stu-id="50584-147">Similarly, the <xref:System.Security.Principal.WindowsIdentity> object also flows across any asynchronous point.</span></span> <span data-ttu-id="50584-148">Quindi, la rappresentazione corrente sul thread, se presente, scorre anche.</span><span class="sxs-lookup"><span data-stu-id="50584-148">Therefore, the current impersonation on the thread, if any, flows too.</span></span>  
  
 <span data-ttu-id="50584-149">È possibile modificare il flusso in due modi:</span><span class="sxs-lookup"><span data-stu-id="50584-149">You can alter the flow in two ways:</span></span>  
  
1. <span data-ttu-id="50584-150">Modificando le <xref:System.Threading.ExecutionContext> impostazioni per escludere il flusso per ogni singolo thread (vedere i <xref:System.Threading.ExecutionContext.SuppressFlow%2A> metodi, <xref:System.Security.SecurityContext.SuppressFlow%2A> e <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> ).</span><span class="sxs-lookup"><span data-stu-id="50584-150">By modifying the <xref:System.Threading.ExecutionContext> settings to suppress the flow on a per-thread basis (see the <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, and <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> methods).</span></span>  
  
2. <span data-ttu-id="50584-151">Modificando la modalità predefinita del processo con la modalità di compatibilità versione 1, in cui l' <xref:System.Security.Principal.WindowsIdentity> oggetto non viene propagato in alcun punto asincrono, indipendentemente dalle <xref:System.Threading.ExecutionContext> impostazioni nel thread corrente.</span><span class="sxs-lookup"><span data-stu-id="50584-151">By changing the process default mode to the version 1 compatibility mode, where the <xref:System.Security.Principal.WindowsIdentity> object does not flow across any asynchronous point, regardless of the <xref:System.Threading.ExecutionContext> settings on the current thread.</span></span> <span data-ttu-id="50584-152">La modalità di modifica della modalità predefinita varia a seconda che si usi un eseguibile gestito o un'interfaccia di hosting non gestita per caricare il CLR:</span><span class="sxs-lookup"><span data-stu-id="50584-152">How you change the default mode depends on whether you use a managed executable or an unmanaged hosting interface to load the CLR:</span></span>  
  
    1. <span data-ttu-id="50584-153">Per i file eseguibili gestiti, è necessario impostare l' `enabled` attributo dell' [\<legacyImpersonationPolicy>](../../configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) elemento su `true` .</span><span class="sxs-lookup"><span data-stu-id="50584-153">For managed executables, you must set the `enabled` attribute of the [\<legacyImpersonationPolicy>](../../configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) element to `true`.</span></span>  
  
    2. <span data-ttu-id="50584-154">Per le interfacce di hosting non gestite, impostare il `STARTUP_LEGACY_IMPERSONATION` flag nel `startupFlags` parametro quando si chiama la `CorBindToRuntimeEx` funzione.</span><span class="sxs-lookup"><span data-stu-id="50584-154">For unmanaged hosting interfaces, set the `STARTUP_LEGACY_IMPERSONATION` flag in the `startupFlags` parameter when calling the `CorBindToRuntimeEx` function.</span></span>  
  
     <span data-ttu-id="50584-155">La modalità di compatibilità versione 1 si applica all'intero processo e a tutti i domini applicazione nel processo.</span><span class="sxs-lookup"><span data-stu-id="50584-155">The version 1 compatibility mode applies to the entire process and to all the application domains in the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50584-156">Requisiti</span><span class="sxs-lookup"><span data-stu-id="50584-156">Requirements</span></span>  
 <span data-ttu-id="50584-157">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50584-157">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50584-158">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="50584-158">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="50584-159">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="50584-159">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="50584-160">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50584-160">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50584-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50584-161">See also</span></span>

- [<span data-ttu-id="50584-162">Funzione CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="50584-162">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)
- [<span data-ttu-id="50584-163">Funzione CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="50584-163">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)
- [<span data-ttu-id="50584-164">Funzione CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="50584-164">CorBindToRuntimeByCfg Function</span></span>](corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="50584-165">Funzione CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="50584-165">CorBindToRuntimeHost Function</span></span>](corbindtoruntimehost-function.md)
- [<span data-ttu-id="50584-166">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="50584-166">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="50584-167">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="50584-167">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)

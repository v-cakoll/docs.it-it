---
title: Funzione CorBindToRuntimeHost
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeHost
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeHost
helpviewer_keywords:
- CorBindToRuntimeHost function [.NET Framework hosting]
ms.assetid: 5c826ba3-8258-49bc-a417-78807915fcaf
topic_type:
- apiref
ms.openlocfilehash: 6566adc442034763e0209869404b60b5afa63866
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176487"
---
# <a name="corbindtoruntimehost-function"></a><span data-ttu-id="0e602-102">Funzione CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="0e602-102">CorBindToRuntimeHost Function</span></span>
<span data-ttu-id="0e602-103">Consente agli host di caricare una versione specificata di Common Language Runtime (CLR) in un processo.</span><span class="sxs-lookup"><span data-stu-id="0e602-103">Enables hosts to load a specified version of the common language runtime (CLR) into a process.</span></span>  
  
 <span data-ttu-id="0e602-104">Questa funzione è stata deprecata in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="0e602-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e602-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0e602-105">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToRuntimeHost (  
    [in] LPCWSTR       pwszVersion,
    [in] LPCWSTR       pwszBuildFlavor,
    [in] LPCWSTR       pwszHostConfigFile,
    [in] VOID*         pReserved,
    [in] DWORD         startupFlags,
    [in] REFCLSID      rclsid,
    [in] REFIID        riid,
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e602-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="0e602-106">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="0e602-107">[in] Stringa che descrive la versione di CLR che si desidera caricare.</span><span class="sxs-lookup"><span data-stu-id="0e602-107">[in] A string that describes the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="0e602-108">Un numero di versione in .NET Framework è costituito da quattro parti separate da punti: *major.minor.build.revision*.</span><span class="sxs-lookup"><span data-stu-id="0e602-108">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="0e602-109">La stringa `pwszVersion` passata come deve iniziare con il carattere "v" seguito dalle prime tre parti del numero di versione (ad esempio, "v1.0.1529").</span><span class="sxs-lookup"><span data-stu-id="0e602-109">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="0e602-110">Alcune versioni di CLR vengono installate con un'istruzione dei criteri che specifica la compatibilità con le versioni precedenti di CLR.</span><span class="sxs-lookup"><span data-stu-id="0e602-110">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="0e602-111">Per impostazione predefinita, lo `pwszVersion` shim di avvio valuta rispetto alle istruzioni dei criteri e carica la versione più recente del runtime compatibile con la versione richiesta.</span><span class="sxs-lookup"><span data-stu-id="0e602-111">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="0e602-112">Un host può forzare lo shim a ignorare `pwszVersion` la valutazione dei criteri `startupFlags` e caricare la versione esatta specificata in passando un valore di STARTUP_LOADER_SAFEMODE per il parametro.</span><span class="sxs-lookup"><span data-stu-id="0e602-112">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of STARTUP_LOADER_SAFEMODE for the `startupFlags` parameter.</span></span>  
  
 <span data-ttu-id="0e602-113">Se `pwszVersion` `null,` il metodo indica che il metodo non carica alcuna versione di CLR.</span><span class="sxs-lookup"><span data-stu-id="0e602-113">If `pwszVersion` is `null,` the method does not load any version of the CLR.</span></span> <span data-ttu-id="0e602-114">Al contrario, restituisce CLR_E_SHIM_RUNTIMELOAD, che indica che non è riuscito a caricare il runtime.</span><span class="sxs-lookup"><span data-stu-id="0e602-114">Instead, it returns CLR_E_SHIM_RUNTIMELOAD, which indicates that it failed to load the runtime.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="0e602-115">[in] Stringa che specifica se caricare il server o la build della workstation di CLR.</span><span class="sxs-lookup"><span data-stu-id="0e602-115">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="0e602-116">I valori validi sono `svr` e `wks`.</span><span class="sxs-lookup"><span data-stu-id="0e602-116">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="0e602-117">La build server è ottimizzata per sfruttare più processori per le operazioni di Garbage Collection e la build workstation è ottimizzata per le applicazioni client in esecuzione su un computer a processore singolo.</span><span class="sxs-lookup"><span data-stu-id="0e602-117">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="0e602-118">Se `pwszBuildFlavor` è impostato su null, viene caricata la build della workstation.</span><span class="sxs-lookup"><span data-stu-id="0e602-118">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="0e602-119">Quando viene eseguita su un computer a processore singolo, la build della workstation viene sempre caricata, anche se `pwszBuildFlavor` è impostata su `svr`.</span><span class="sxs-lookup"><span data-stu-id="0e602-119">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="0e602-120">Tuttavia, `pwszBuildFlavor` se `svr` è impostata su e viene specificata `startupFlags` l'operazione di Garbage Collection simultanea (vedere la descrizione del parametro), viene caricata la compilazione del server.</span><span class="sxs-lookup"><span data-stu-id="0e602-120">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `startupFlags` parameter), the server build is loaded.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0e602-121">La Garbage Collection simultanea non è supportata nelle applicazioni che eseguono l'emulatore WOW64 x86 su sistemi a 64 bit che implementano l'architettura Intel Itanium (precedentemente denominata IA-64).</span><span class="sxs-lookup"><span data-stu-id="0e602-121">Concurrent garbage collection is not supported in applications running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="0e602-122">Per ulteriori informazioni sull'utilizzo di WOW64 nei sistemi Windows a 64 bit, vedere Esecuzione di applicazioni a [32 bit](/windows/desktop/WinProg64/running-32-bit-applications).</span><span class="sxs-lookup"><span data-stu-id="0e602-122">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](/windows/desktop/WinProg64/running-32-bit-applications).</span></span>  
  
 `pwszHostConfigFile`  
 <span data-ttu-id="0e602-123">[in] Nome di un file di configurazione host che specifica la versione di CLR da caricare.</span><span class="sxs-lookup"><span data-stu-id="0e602-123">[in] The name of a host configuration file that specifies the version of the CLR to load.</span></span> <span data-ttu-id="0e602-124">Se il nome del file non include un percorso completo, si presuppone che il file si trova nella stessa directory dell'eseguibile che sta effettuando la chiamata.</span><span class="sxs-lookup"><span data-stu-id="0e602-124">If the file name does not include a fully qualified path, the file is assumed to be in the same directory as the executable that is making the call.</span></span>  
  
 `pReserved`  
 <span data-ttu-id="0e602-125">[in] Riservato per l'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="0e602-125">[in] Reserved for future extensibility.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="0e602-126">[in] Set di flag che controlla la Garbage Collection simultanea, il `pwszVersion` codice indipendente dal dominio e il comportamento del parametro.</span><span class="sxs-lookup"><span data-stu-id="0e602-126">[in] A set of flags that controls concurrent garbage collection, domain-neutral code, and the behavior of the `pwszVersion` parameter.</span></span> <span data-ttu-id="0e602-127">Il valore predefinito è dominio singolo se non è impostato alcun flag.</span><span class="sxs-lookup"><span data-stu-id="0e602-127">The default is single domain if no flag is set.</span></span> <span data-ttu-id="0e602-128">Per un elenco dei valori supportati, vedere [l'enumerazione STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="0e602-128">For a list of supported values, see the [STARTUP_FLAGS enumeration](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md).</span></span>  
  
 `rclsid`  
 <span data-ttu-id="0e602-129">[in] La `CLSID` della coclasse che implementa il [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) o [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="0e602-129">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="0e602-130">I valori supportati sono CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="0e602-130">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="0e602-131">[in] L'interfaccia `IID` che si sta richiedendo.</span><span class="sxs-lookup"><span data-stu-id="0e602-131">[in] The `IID` of the interface you are requesting.</span></span> <span data-ttu-id="0e602-132">I valori supportati sono IID_ICorRuntimeHost o IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="0e602-132">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="0e602-133">[fuori] Puntatore a interfaccia alla versione del runtime caricata.</span><span class="sxs-lookup"><span data-stu-id="0e602-133">[out] An interface pointer to the version of the runtime that was loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e602-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0e602-134">Requirements</span></span>  
 <span data-ttu-id="0e602-135">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e602-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e602-136">**Intestazione:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="0e602-136">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="0e602-137">**Biblioteca:** Mscoree</span><span class="sxs-lookup"><span data-stu-id="0e602-137">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0e602-138">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e602-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e602-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e602-139">See also</span></span>

- [<span data-ttu-id="0e602-140">Funzione CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="0e602-140">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="0e602-141">Funzione CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="0e602-141">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [<span data-ttu-id="0e602-142">Funzione CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="0e602-142">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="0e602-143">Funzione CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="0e602-143">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="0e602-144">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="0e602-144">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="0e602-145">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="0e602-145">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

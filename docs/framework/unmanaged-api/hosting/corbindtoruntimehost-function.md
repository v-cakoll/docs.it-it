---
title: Funzione CorBindToRuntimeHost
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e6d69f39aa74665843b0bf91407e764ea67f41d7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="corbindtoruntimehost-function"></a><span data-ttu-id="0ec3f-102">Funzione CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="0ec3f-102">CorBindToRuntimeHost Function</span></span>
<span data-ttu-id="0ec3f-103">Consente agli host di caricare una versione specifica di common language runtime (CLR) in un processo.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-103">Enables hosts to load a specified version of the common language runtime (CLR) into a process.</span></span>  
  
 <span data-ttu-id="0ec3f-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ec3f-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ec3f-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0ec3f-105">Syntax</span></span>  
  
```  
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
  
#### <a name="parameters"></a><span data-ttu-id="0ec3f-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="0ec3f-106">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="0ec3f-107">[in] Una stringa che descrive la versione di CLR a cui si desidera caricare.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-107">[in] A string that describes the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="0ec3f-108">Un numero di versione di .NET Framework è costituito da quattro parti separate da punti: *revisione*.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-108">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="0ec3f-109">La stringa passata come `pwszVersion` deve iniziare con il carattere "v" seguito dalle prime tre parti del numero di versione (ad esempio, "v 1.0.1529").</span><span class="sxs-lookup"><span data-stu-id="0ec3f-109">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="0ec3f-110">Alcune versioni di Common Language Runtime vengono installati con un'istruzione di criteri che specifica la compatibilità con le versioni precedenti di CLR.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-110">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="0ec3f-111">Per impostazione predefinita, valuta lo shim di avvio `pwszVersion` contro istruzioni dei criteri e carica la versione più recente del runtime che è compatibile con la versione richiesta.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-111">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="0ec3f-112">Un host può imporre allo shim di ignorare la valutazione dei criteri e caricare l'esatta versione specificata `pwszVersion` passando un valore STARTUP_LOADER_SAFEMODE per il `startupFlags` parametro.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-112">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of STARTUP_LOADER_SAFEMODE for the `startupFlags` parameter.</span></span>  
  
 <span data-ttu-id="0ec3f-113">Se `pwszVersion` è `null,` il metodo non viene caricato qualsiasi versione di CLR.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-113">If `pwszVersion` is `null,` the method does not load any version of the CLR.</span></span> <span data-ttu-id="0ec3f-114">Restituisce invece CLR_E_SHIM_RUNTIMELOAD, che indica che non è riuscito a caricare il runtime.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-114">Instead, it returns CLR_E_SHIM_RUNTIMELOAD, which indicates that it failed to load the runtime.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="0ec3f-115">[in] Stringa che specifica se caricare il server o la compilazione di workstation di CLR.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-115">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="0ec3f-116">I valori validi sono `svr` e `wks`.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-116">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="0ec3f-117">La compilazione di server è ottimizzata per sfruttare i vantaggi di più processori per operazioni di garbage collection e la compilazione di workstation è ottimizzata per le applicazioni client eseguite in un computer a processore singolo.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-117">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="0ec3f-118">Se `pwszBuildFlavor` è impostato su null, viene caricata la build per workstation.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-118">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="0ec3f-119">Quando si esegue in un computer a processore singolo, la compilazione della workstation viene sempre caricata, anche se `pwszBuildFlavor` è impostato su `svr`.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-119">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="0ec3f-120">Tuttavia, se `pwszBuildFlavor` è impostato su `svr` e garbage collection simultanea è specificata (vedere la descrizione del `startupFlags` parametro), verrà caricata la build del server.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-120">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `startupFlags` parameter), the server build is loaded.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ec3f-121">Garbage collection simultanea non è supportata nelle applicazioni in esecuzione WOW64 x86 emulatore nei sistemi a 64 bit che implementano l'architettura Intel Itanium (IA-64 noto).</span><span class="sxs-lookup"><span data-stu-id="0ec3f-121">Concurrent garbage collection is not supported in applications running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="0ec3f-122">Per ulteriori informazioni sull'utilizzo di WOW64 nei sistemi Windows a 64 bit, vedere [applicazioni in esecuzione a 32 bit](http://msdn.microsoft.com/library/windows/desktop/aa384249.aspx).</span><span class="sxs-lookup"><span data-stu-id="0ec3f-122">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](http://msdn.microsoft.com/library/windows/desktop/aa384249.aspx).</span></span>  
  
 `pwszHostConfigFile`  
 <span data-ttu-id="0ec3f-123">[in] Il nome di un file di configurazione di host che specifica la versione di Common Language Runtime da caricare.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-123">[in] The name of a host configuration file that specifies the version of the CLR to load.</span></span> <span data-ttu-id="0ec3f-124">Se il nome del file non include il percorso completo, il file è considerato nella stessa directory del file eseguibile che effettua la chiamata.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-124">If the file name does not include a fully qualified path, the file is assumed to be in the same directory as the executable that is making the call.</span></span>  
  
 `pReserved`  
 <span data-ttu-id="0ec3f-125">[in] Riservato per l'estensibilità futura.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-125">[in] Reserved for future extensibility.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="0ec3f-126">[in] Un set di flag che controlla il comportamento di garbage collection simultanea e codice indipendente dal dominio di `pwszVersion` parametro.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-126">[in] A set of flags that controls concurrent garbage collection, domain-neutral code, and the behavior of the `pwszVersion` parameter.</span></span> <span data-ttu-id="0ec3f-127">Se non è impostato alcun flag, il valore predefinito è singolo dominio.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-127">The default is single domain if no flag is set.</span></span> <span data-ttu-id="0ec3f-128">Per un elenco di valori supportati, vedere il [enumerazione STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="0ec3f-128">For a list of supported values, see the [STARTUP_FLAGS enumeration](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md).</span></span>  
  
 `rclsid`  
 <span data-ttu-id="0ec3f-129">[in] Il `CLSID` della coclasse che implementa il [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) o [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-129">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="0ec3f-130">Valori supportati sono CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-130">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="0ec3f-131">[in] Il `IID` dell'interfaccia richiesta.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-131">[in] The `IID` of the interface you are requesting.</span></span> <span data-ttu-id="0ec3f-132">Valori supportati sono IID_ICorRuntimeHost o IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-132">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="0ec3f-133">[out] Un puntatore a interfaccia per la versione del runtime che è stato caricato.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-133">[out] An interface pointer to the version of the runtime that was loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ec3f-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0ec3f-134">Requirements</span></span>  
 <span data-ttu-id="0ec3f-135">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ec3f-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ec3f-136">**Intestazione:** Mscoree</span><span class="sxs-lookup"><span data-stu-id="0ec3f-136">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="0ec3f-137">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0ec3f-137">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ec3f-138">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ec3f-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ec3f-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ec3f-139">See Also</span></span>  
 [<span data-ttu-id="0ec3f-140">Funzione CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="0ec3f-140">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 [<span data-ttu-id="0ec3f-141">Funzione CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="0ec3f-141">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 [<span data-ttu-id="0ec3f-142">Funzione CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="0ec3f-142">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 [<span data-ttu-id="0ec3f-143">Funzione CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="0ec3f-143">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [<span data-ttu-id="0ec3f-144">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="0ec3f-144">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [<span data-ttu-id="0ec3f-145">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="0ec3f-145">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

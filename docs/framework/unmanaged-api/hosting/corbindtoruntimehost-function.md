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
ms.openlocfilehash: 9d1c7f4f5b881f7f55539602c152b557a7950472
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504407"
---
# <a name="corbindtoruntimehost-function"></a><span data-ttu-id="ec163-102">Funzione CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="ec163-102">CorBindToRuntimeHost Function</span></span>
<span data-ttu-id="ec163-103">Consente agli host di caricare una versione specificata del Common Language Runtime (CLR) in un processo.</span><span class="sxs-lookup"><span data-stu-id="ec163-103">Enables hosts to load a specified version of the common language runtime (CLR) into a process.</span></span>  
  
 <span data-ttu-id="ec163-104">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="ec163-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec163-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ec163-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="ec163-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ec163-106">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="ec163-107">in Stringa che descrive la versione di CLR che si desidera caricare.</span><span class="sxs-lookup"><span data-stu-id="ec163-107">[in] A string that describes the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="ec163-108">Un numero di versione nel .NET Framework è costituito da quattro parti separate da punti: *Major. minor. Build. Revision*.</span><span class="sxs-lookup"><span data-stu-id="ec163-108">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="ec163-109">La stringa passata come `pwszVersion` deve iniziare con il carattere "v" seguito dalle prime tre parti del numero di versione (ad esempio, "v 1.0.1529").</span><span class="sxs-lookup"><span data-stu-id="ec163-109">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="ec163-110">Alcune versioni di CLR vengono installate con un'istruzione di criteri che specifica la compatibilità con le versioni precedenti di CLR.</span><span class="sxs-lookup"><span data-stu-id="ec163-110">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="ec163-111">Per impostazione predefinita, lo shim di avvio valuta le `pwszVersion` istruzioni dei criteri e carica la versione più recente del runtime compatibile con la versione richiesta.</span><span class="sxs-lookup"><span data-stu-id="ec163-111">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="ec163-112">Un host può forzare lo shim a ignorare la valutazione dei criteri e caricare la versione esatta specificata in `pwszVersion` passando il valore STARTUP_LOADER_SAFEMODE per il `startupFlags` parametro.</span><span class="sxs-lookup"><span data-stu-id="ec163-112">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of STARTUP_LOADER_SAFEMODE for the `startupFlags` parameter.</span></span>  
  
 <span data-ttu-id="ec163-113">Se `pwszVersion` è `null,` , il metodo non carica alcuna versione di CLR.</span><span class="sxs-lookup"><span data-stu-id="ec163-113">If `pwszVersion` is `null,` the method does not load any version of the CLR.</span></span> <span data-ttu-id="ec163-114">Restituisce invece CLR_E_SHIM_RUNTIMELOAD, che indica che non è stato possibile caricare il Runtime.</span><span class="sxs-lookup"><span data-stu-id="ec163-114">Instead, it returns CLR_E_SHIM_RUNTIMELOAD, which indicates that it failed to load the runtime.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="ec163-115">in Stringa che specifica se caricare il server o la build della workstation di CLR.</span><span class="sxs-lookup"><span data-stu-id="ec163-115">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="ec163-116">I valori validi sono `svr` e `wks`.</span><span class="sxs-lookup"><span data-stu-id="ec163-116">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="ec163-117">La compilazione server è ottimizzata per sfruttare i vantaggi di più processori per le operazioni di Garbage Collection e la compilazione della workstation è ottimizzata per le applicazioni client in esecuzione su un computer a processore singolo.</span><span class="sxs-lookup"><span data-stu-id="ec163-117">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="ec163-118">Se `pwszBuildFlavor` è impostato su null, viene caricata la compilazione della workstation.</span><span class="sxs-lookup"><span data-stu-id="ec163-118">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="ec163-119">Quando è in esecuzione in un computer a processore singolo, la compilazione della workstation viene sempre caricata, anche se `pwszBuildFlavor` è impostato su `svr` .</span><span class="sxs-lookup"><span data-stu-id="ec163-119">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="ec163-120">Tuttavia, se `pwszBuildFlavor` è impostato su `svr` e viene specificato Garbage Collection simultaneo (vedere la descrizione del `startupFlags` parametro), viene caricata la compilazione del server.</span><span class="sxs-lookup"><span data-stu-id="ec163-120">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `startupFlags` parameter), the server build is loaded.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ec163-121">La Garbage Collection simultanea non è supportata nelle applicazioni che eseguono l'emulatore WOW64 x86 nei sistemi a 64 bit che implementano l'architettura Intel Itanium (denominata in precedenza IA-64).</span><span class="sxs-lookup"><span data-stu-id="ec163-121">Concurrent garbage collection is not supported in applications running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="ec163-122">Per ulteriori informazioni sull'utilizzo di WOW64 in sistemi Windows a 64 bit, vedere [esecuzione di applicazioni a 32 bit](/windows/desktop/WinProg64/running-32-bit-applications).</span><span class="sxs-lookup"><span data-stu-id="ec163-122">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](/windows/desktop/WinProg64/running-32-bit-applications).</span></span>  
  
 `pwszHostConfigFile`  
 <span data-ttu-id="ec163-123">in Nome di un file di configurazione host che specifica la versione di CLR da caricare.</span><span class="sxs-lookup"><span data-stu-id="ec163-123">[in] The name of a host configuration file that specifies the version of the CLR to load.</span></span> <span data-ttu-id="ec163-124">Se il nome file non include un percorso completo, si presuppone che il file si trovi nella stessa directory del file eseguibile che effettua la chiamata.</span><span class="sxs-lookup"><span data-stu-id="ec163-124">If the file name does not include a fully qualified path, the file is assumed to be in the same directory as the executable that is making the call.</span></span>  
  
 `pReserved`  
 <span data-ttu-id="ec163-125">in Riservato per l'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="ec163-125">[in] Reserved for future extensibility.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="ec163-126">in Set di flag che controlla il Garbage Collection simultaneo, il codice indipendente dal dominio e il comportamento del `pwszVersion` parametro.</span><span class="sxs-lookup"><span data-stu-id="ec163-126">[in] A set of flags that controls concurrent garbage collection, domain-neutral code, and the behavior of the `pwszVersion` parameter.</span></span> <span data-ttu-id="ec163-127">Il valore predefinito è Single Domain se non è impostato alcun flag.</span><span class="sxs-lookup"><span data-stu-id="ec163-127">The default is single domain if no flag is set.</span></span> <span data-ttu-id="ec163-128">Per un elenco dei valori supportati, vedere l' [enumerazione STARTUP_FLAGS](startup-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="ec163-128">For a list of supported values, see the [STARTUP_FLAGS enumeration](startup-flags-enumeration.md).</span></span>  
  
 `rclsid`  
 <span data-ttu-id="ec163-129">in `CLSID`Della coclasse che implementa l'interfaccia [ICorRuntimeHost](icorruntimehost-interface.md) o [ICLRRuntimeHost](iclrruntimehost-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="ec163-129">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](icorruntimehost-interface.md) or the [ICLRRuntimeHost](iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="ec163-130">I valori supportati sono CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="ec163-130">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="ec163-131">in `IID`Dell'interfaccia richiesta.</span><span class="sxs-lookup"><span data-stu-id="ec163-131">[in] The `IID` of the interface you are requesting.</span></span> <span data-ttu-id="ec163-132">I valori supportati sono IID_ICorRuntimeHost o IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="ec163-132">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="ec163-133">out Puntatore di interfaccia alla versione del runtime che è stata caricata.</span><span class="sxs-lookup"><span data-stu-id="ec163-133">[out] An interface pointer to the version of the runtime that was loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec163-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ec163-134">Requirements</span></span>  
 <span data-ttu-id="ec163-135">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec163-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec163-136">**Intestazione:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="ec163-136">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="ec163-137">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ec163-137">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ec163-138">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec163-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec163-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec163-139">See also</span></span>

- [<span data-ttu-id="ec163-140">Funzione CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="ec163-140">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)
- [<span data-ttu-id="ec163-141">Funzione CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="ec163-141">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)
- [<span data-ttu-id="ec163-142">Funzione CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="ec163-142">CorBindToRuntimeByCfg Function</span></span>](corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="ec163-143">Funzione CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="ec163-143">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="ec163-144">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="ec163-144">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="ec163-145">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="ec163-145">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)

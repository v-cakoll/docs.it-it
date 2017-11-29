---
title: Metodo IHostAssemblyStore::ProvideModule
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostAssemblyStore.ProvideModule
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostAssemblyStore::ProvideModule
helpviewer_keywords:
- IHostAssemblyStore::ProvideModule method [.NET Framework hosting]
- ProvideModule method [.NET Framework hosting]
ms.assetid: f42e3dd0-c88e-4748-b6c0-4c515a633180
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6894d15221b8ace12e76b8eba4ac69503eaa792d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostassemblystoreprovidemodule-method"></a><span data-ttu-id="4a8ac-102">Metodo IHostAssemblyStore::ProvideModule</span><span class="sxs-lookup"><span data-stu-id="4a8ac-102">IHostAssemblyStore::ProvideModule Method</span></span>
<span data-ttu-id="4a8ac-103">Risolve un file di risorse all'interno di un assembly o collegato (ma non incorporato).</span><span class="sxs-lookup"><span data-stu-id="4a8ac-103">Resolves a module within an assembly or a linked (but not an embedded) resource file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a8ac-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4a8ac-104">Syntax</span></span>  
  
```  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4a8ac-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4a8ac-105">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="4a8ac-106">[in] Un puntatore a un [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) istanza che descrive il modulo di richiesto <xref:System.AppDomain>, assembly e il nome del modulo.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-106">[in] A pointer to a [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) instance that describes the requested module's <xref:System.AppDomain>, assembly, and module name.</span></span>  
  
 `pdwModuleId`  
 <span data-ttu-id="4a8ac-107">[out] Un puntatore a un identificatore univoco per il `IStream` contenente il modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-107">[out] A pointer to a unique identifier for the `IStream` containing the loaded module.</span></span>  
  
 `ppStmModuleImage`  
 <span data-ttu-id="4a8ac-108">[out] Un puntatore all'indirizzo di un `IStream` , che contiene l'immagine eseguibile portabile (PE) da caricare, o null se non è stato possibile trovare il modulo.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-108">[out] A pointer to the address of an `IStream` object, which contains the portable executable (PE) image to be loaded, or null if the module could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="4a8ac-109">[out] Un puntatore all'indirizzo di un `IStream` dell'oggetto, che contiene le informazioni di debug (PDB) del programma per il modulo richiesto oppure null se non è stato possibile trovare il file con estensione pdb.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-109">[out] A pointer to the address of an `IStream` object, which contains the program debug (PDB) information for the requested module, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4a8ac-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4a8ac-110">Return Value</span></span>  
  
|<span data-ttu-id="4a8ac-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4a8ac-111">HRESULT</span></span>|<span data-ttu-id="4a8ac-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a8ac-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4a8ac-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="4a8ac-113">S_OK</span></span>|<span data-ttu-id="4a8ac-114">`ProvideModule`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-114">`ProvideModule` returned successfully.</span></span>|  
|<span data-ttu-id="4a8ac-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4a8ac-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4a8ac-116">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4a8ac-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4a8ac-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4a8ac-118">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-118">The call timed out.</span></span>|  
|<span data-ttu-id="4a8ac-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4a8ac-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4a8ac-120">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4a8ac-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4a8ac-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4a8ac-122">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4a8ac-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4a8ac-123">E_FAIL</span></span>|<span data-ttu-id="4a8ac-124">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4a8ac-125">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4a8ac-126">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4a8ac-127">COR_E_FILENOTFOUND (0X80070002)</span><span class="sxs-lookup"><span data-stu-id="4a8ac-127">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="4a8ac-128">L'assembly richiesto o una risorsa collegata non è possibile individuare.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-128">The requested assembly or linked resource could not be located.</span></span>|  
|<span data-ttu-id="4a8ac-129">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="4a8ac-129">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="4a8ac-130">`pdwModuleId`non è sufficientemente grande da contenere l'identificatore in cui l'host deve essere restituito.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-130">`pdwModuleId` is not large enough to contain the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a8ac-131">Note</span><span class="sxs-lookup"><span data-stu-id="4a8ac-131">Remarks</span></span>  
 <span data-ttu-id="4a8ac-132">Il valore di identità restituito per `pdwModuleId` è specificato dall'host.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-132">The identity value returned for `pdwModuleId` is specified by the host.</span></span> <span data-ttu-id="4a8ac-133">Gli identificatori devono essere univoci all'interno della durata di un processo.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-133">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="4a8ac-134">Common Language Runtime utilizza questo valore come identificatore univoco per il flusso associato.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-134">The CLR uses this value as the unique identifier for the associated stream.</span></span> <span data-ttu-id="4a8ac-135">Ogni valore viene confrontato con i valori per `pAssemblyId` restituiti dalle chiamate a [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) e con i valori per `pdwModuleId` restituito da altre chiamate a `ProvideModule`.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-135">It checks each value against the values for `pAssemblyId` returned by calls to [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) and against the values for `pdwModuleId` returned by other calls to `ProvideModule`.</span></span> <span data-ttu-id="4a8ac-136">Se l'host restituisce lo stesso valore di identificatore per un'altra `IStream`, CLR verifica se il contenuto del flusso è già stato mappato.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-136">If the host returns the same identifier value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="4a8ac-137">In questo caso, CLR carica la copia esistente dell'immagine anziché eseguire il mapping uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-137">If so, the CLR loads the existing copy of the image instead of mapping a new one.</span></span> <span data-ttu-id="4a8ac-138">Pertanto, l'identificatore non deve sovrapporsi agli identificatori assembly restituiti da `ProvideAssembly`.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-138">Therefore, the identifier must also not overlap with the assembly identifiers returned from `ProvideAssembly`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a8ac-139">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4a8ac-139">Requirements</span></span>  
 <span data-ttu-id="4a8ac-140">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a8ac-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a8ac-141">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="4a8ac-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4a8ac-142">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4a8ac-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a8ac-143">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a8ac-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a8ac-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a8ac-144">See Also</span></span>  
 [<span data-ttu-id="4a8ac-145">ICLRAssemblyReferenceList (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="4a8ac-145">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="4a8ac-146">IHostAssemblyManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="4a8ac-146">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="4a8ac-147">IHostAssemblyStore (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="4a8ac-147">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)

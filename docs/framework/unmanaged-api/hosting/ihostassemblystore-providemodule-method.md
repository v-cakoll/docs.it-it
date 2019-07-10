---
title: Metodo IHostAssemblyStore::ProvideModule
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore.ProvideModule
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideModule
helpviewer_keywords:
- IHostAssemblyStore::ProvideModule method [.NET Framework hosting]
- ProvideModule method [.NET Framework hosting]
ms.assetid: f42e3dd0-c88e-4748-b6c0-4c515a633180
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9290fd70b17b5a6456d85cb4b037ebbc62e028f8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763981"
---
# <a name="ihostassemblystoreprovidemodule-method"></a><span data-ttu-id="ef609-102">Metodo IHostAssemblyStore::ProvideModule</span><span class="sxs-lookup"><span data-stu-id="ef609-102">IHostAssemblyStore::ProvideModule Method</span></span>
<span data-ttu-id="ef609-103">Risolve un file di risorse modulo all'interno di un assembly o un collegato (ma non incorporato).</span><span class="sxs-lookup"><span data-stu-id="ef609-103">Resolves a module within an assembly or a linked (but not an embedded) resource file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef609-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ef609-104">Syntax</span></span>  
  
```cpp  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef609-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ef609-105">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="ef609-106">[in] Un puntatore a un [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) istanza che descrive il modulo richiesto <xref:System.AppDomain>, assembly e il nome del modulo.</span><span class="sxs-lookup"><span data-stu-id="ef609-106">[in] A pointer to a [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) instance that describes the requested module's <xref:System.AppDomain>, assembly, and module name.</span></span>  
  
 `pdwModuleId`  
 <span data-ttu-id="ef609-107">[out] Un puntatore a un identificatore univoco per il `IStream` contenente il modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="ef609-107">[out] A pointer to a unique identifier for the `IStream` containing the loaded module.</span></span>  
  
 `ppStmModuleImage`  
 <span data-ttu-id="ef609-108">[out] Un puntatore all'indirizzo di un `IStream` dell'oggetto, che contiene l'immagine del file eseguibile portabile (PE) di essere caricati oppure null se non è stato possibile trovare il modulo.</span><span class="sxs-lookup"><span data-stu-id="ef609-108">[out] A pointer to the address of an `IStream` object, which contains the portable executable (PE) image to be loaded, or null if the module could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="ef609-109">[out] Un puntatore all'indirizzo di un `IStream` dell'oggetto, che contiene le informazioni di debug (PDB) del programma per il modulo richiesto o null se il file con estensione PDB non è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="ef609-109">[out] A pointer to the address of an `IStream` object, which contains the program debug (PDB) information for the requested module, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ef609-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ef609-110">Return Value</span></span>  
  
|<span data-ttu-id="ef609-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ef609-111">HRESULT</span></span>|<span data-ttu-id="ef609-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ef609-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ef609-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="ef609-113">S_OK</span></span>|<span data-ttu-id="ef609-114">`ProvideModule` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="ef609-114">`ProvideModule` returned successfully.</span></span>|  
|<span data-ttu-id="ef609-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ef609-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ef609-116">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="ef609-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ef609-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ef609-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ef609-118">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="ef609-118">The call timed out.</span></span>|  
|<span data-ttu-id="ef609-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ef609-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ef609-120">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="ef609-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ef609-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ef609-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ef609-122">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="ef609-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ef609-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ef609-123">E_FAIL</span></span>|<span data-ttu-id="ef609-124">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="ef609-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ef609-125">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="ef609-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ef609-126">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ef609-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ef609-127">COR_E_FILENOTFOUND (0x80070002)</span><span class="sxs-lookup"><span data-stu-id="ef609-127">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="ef609-128">L'assembly richiesto o risorsa collegata non è possibile individuare.</span><span class="sxs-lookup"><span data-stu-id="ef609-128">The requested assembly or linked resource could not be located.</span></span>|  
|<span data-ttu-id="ef609-129">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="ef609-129">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="ef609-130">`pdwModuleId` non è sufficientemente grande da contenere l'identificatore che l'host deve essere restituito.</span><span class="sxs-lookup"><span data-stu-id="ef609-130">`pdwModuleId` is not large enough to contain the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef609-131">Note</span><span class="sxs-lookup"><span data-stu-id="ef609-131">Remarks</span></span>  
 <span data-ttu-id="ef609-132">Il valore identity restituiti per `pdwModuleId` è specificato dall'host.</span><span class="sxs-lookup"><span data-stu-id="ef609-132">The identity value returned for `pdwModuleId` is specified by the host.</span></span> <span data-ttu-id="ef609-133">Gli identificatori devono essere univoci all'interno della durata di un processo.</span><span class="sxs-lookup"><span data-stu-id="ef609-133">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="ef609-134">Common Language Runtime Usa questo valore come l'identificatore univoco per il flusso associato.</span><span class="sxs-lookup"><span data-stu-id="ef609-134">The CLR uses this value as the unique identifier for the associated stream.</span></span> <span data-ttu-id="ef609-135">Ogni valore viene confrontato con i valori per `pAssemblyId` restituiti dalle chiamate a [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) e con i valori di `pdwModuleId` restituito da altre chiamate a `ProvideModule`.</span><span class="sxs-lookup"><span data-stu-id="ef609-135">It checks each value against the values for `pAssemblyId` returned by calls to [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) and against the values for `pdwModuleId` returned by other calls to `ProvideModule`.</span></span> <span data-ttu-id="ef609-136">Se l'host restituisce lo stesso valore di identificatore per un altro `IStream`, Common Language Runtime controlla se il contenuto del flusso è già stato mappato.</span><span class="sxs-lookup"><span data-stu-id="ef609-136">If the host returns the same identifier value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="ef609-137">In questo caso, CLR caricata la copia esistente di immagine anziché eseguire il mapping di una nuova.</span><span class="sxs-lookup"><span data-stu-id="ef609-137">If so, the CLR loads the existing copy of the image instead of mapping a new one.</span></span> <span data-ttu-id="ef609-138">Pertanto, l'identificatore non deve sovrapporsi con gli identificatori di assembly restituiti da `ProvideAssembly`.</span><span class="sxs-lookup"><span data-stu-id="ef609-138">Therefore, the identifier must also not overlap with the assembly identifiers returned from `ProvideAssembly`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef609-139">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ef609-139">Requirements</span></span>  
 <span data-ttu-id="ef609-140">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef609-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef609-141">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ef609-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ef609-142">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="ef609-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ef609-143">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef609-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef609-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef609-144">See also</span></span>

- [<span data-ttu-id="ef609-145">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="ef609-145">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="ef609-146">Interfaccia IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="ef609-146">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="ef609-147">Interfaccia IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="ef609-147">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)

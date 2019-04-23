---
title: Metodo IHostAssemblyStore::ProvideAssembly
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore.ProvideAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideAssembly
helpviewer_keywords:
- ProvideAssembly method [.NET Framework hosting]
- IHostAssemblyStore::ProvideAssembly method [.NET Framework hosting]
ms.assetid: 625c3dd5-a3f0-442c-adde-310dadbb5054
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 62a8be1e330338043df50bd80576b5aa65447b9c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59111904"
---
# <a name="ihostassemblystoreprovideassembly-method"></a><span data-ttu-id="d0fef-102">Metodo IHostAssemblyStore::ProvideAssembly</span><span class="sxs-lookup"><span data-stu-id="d0fef-102">IHostAssemblyStore::ProvideAssembly Method</span></span>
<span data-ttu-id="d0fef-103">Ottiene un riferimento a un assembly che non fa riferimento il [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) restituito da [IHostAssemblyManager](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span><span class="sxs-lookup"><span data-stu-id="d0fef-103">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that is returned from [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span> <span data-ttu-id="d0fef-104">Common language runtime (CLR) chiama `ProvideAssembly` per ogni assembly che non compare nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="d0fef-104">The common language runtime (CLR) calls `ProvideAssembly` for each assembly that does not appear in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0fef-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d0fef-105">Syntax</span></span>  
  
```  
HRESULT ProvideAssembly (  
    [in]  AssemblyBindInfo *pBindInfo,  
    [out] UINT64           *pAssemblyId,  
    [out] UINT64           *pHostContext,  
    [out] IStream          **ppStmAssemblyImage,  
    [out] IStream          **ppStmPDB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0fef-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="d0fef-106">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="d0fef-107">[in] Un puntatore a un [AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) istanza usato dall'host per determinare alcune caratteristiche di associazione, tra cui la presenza o assenza di qualsiasi criterio di controllo delle versioni e l'assembly a cui associarsi.</span><span class="sxs-lookup"><span data-stu-id="d0fef-107">[in] A pointer to an [AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) instance that the host uses to determine certain bind characteristics, including the presence or absence of any versioning policy, and which assembly to bind to.</span></span>  
  
 `pAssemblyId`  
 <span data-ttu-id="d0fef-108">[out] Un puntatore a un identificatore univoco per l'assembly richiesto per l'oggetto `IStream`.</span><span class="sxs-lookup"><span data-stu-id="d0fef-108">[out] A pointer to a unique identifier for the requested assembly for this `IStream`.</span></span>  
  
 `pHostContext`  
 <span data-ttu-id="d0fef-109">[out] Un puntatore ai dati specifici per l'host utilizzato per determinare l'evidenza dell'assembly richiesto senza la necessità di una piattaforma chiamata invoke.</span><span class="sxs-lookup"><span data-stu-id="d0fef-109">[out] A pointer to host-specific data that is used to determine the evidence of the requested assembly without the need of a platform invoke call.</span></span> <span data-ttu-id="d0fef-110">`pHostContext` corrisponde alla <xref:System.Reflection.Assembly.HostContext%2A> proprietà di gestito <xref:System.Reflection.Assembly> classe.</span><span class="sxs-lookup"><span data-stu-id="d0fef-110">`pHostContext` corresponds to the <xref:System.Reflection.Assembly.HostContext%2A> property of the managed <xref:System.Reflection.Assembly> class.</span></span>  
  
 `ppStmAssemblyImage`  
 <span data-ttu-id="d0fef-111">[out] Un puntatore all'indirizzo di un `IStream` che contiene l'immagine eseguibile portabile (PE) da caricare, oppure null se non è stato possibile trovare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="d0fef-111">[out] A pointer to the address of an `IStream` that contains the portable executable (PE) image to be loaded, or null if the assembly could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="d0fef-112">[out] Un puntatore all'indirizzo di un `IStream` che contiene le informazioni di debug (PDB) di programma, o null se non è stato possibile trovare il file con estensione pdb.</span><span class="sxs-lookup"><span data-stu-id="d0fef-112">[out] A pointer to the address of an `IStream` that contains the program debug (PDB) information, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0fef-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d0fef-113">Return Value</span></span>  
  
|<span data-ttu-id="d0fef-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d0fef-114">HRESULT</span></span>|<span data-ttu-id="d0fef-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d0fef-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d0fef-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="d0fef-116">S_OK</span></span>|<span data-ttu-id="d0fef-117">`ProvideAssembly` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="d0fef-117">`ProvideAssembly` returned successfully.</span></span>|  
|<span data-ttu-id="d0fef-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d0fef-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d0fef-119">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="d0fef-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d0fef-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d0fef-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d0fef-121">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="d0fef-121">The call timed out.</span></span>|  
|<span data-ttu-id="d0fef-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d0fef-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d0fef-123">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="d0fef-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d0fef-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d0fef-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d0fef-125">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="d0fef-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d0fef-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d0fef-126">E_FAIL</span></span>|<span data-ttu-id="d0fef-127">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="d0fef-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d0fef-128">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="d0fef-128">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d0fef-129">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d0fef-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d0fef-130">COR_E_FILENOTFOUND (0x80070002)</span><span class="sxs-lookup"><span data-stu-id="d0fef-130">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="d0fef-131">Impossibile individuare l'assembly richiesto.</span><span class="sxs-lookup"><span data-stu-id="d0fef-131">The requested assembly could not be located.</span></span>|  
|<span data-ttu-id="d0fef-132">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="d0fef-132">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="d0fef-133">Le dimensioni del buffer specificata da `pAssemblyId` non è sufficientemente grande da contenere l'identificatore che l'host deve essere restituito.</span><span class="sxs-lookup"><span data-stu-id="d0fef-133">The buffer size specified by `pAssemblyId` is not large enough to hold the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0fef-134">Note</span><span class="sxs-lookup"><span data-stu-id="d0fef-134">Remarks</span></span>  
 <span data-ttu-id="d0fef-135">Il valore identity restituiti per `pAssemblyId` è specificato dall'host.</span><span class="sxs-lookup"><span data-stu-id="d0fef-135">The identity value returned for `pAssemblyId` is specified by the host.</span></span> <span data-ttu-id="d0fef-136">Gli identificatori devono essere univoci all'interno della durata di un processo.</span><span class="sxs-lookup"><span data-stu-id="d0fef-136">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="d0fef-137">Common Language Runtime Usa questo valore come un identificatore univoco per il flusso.</span><span class="sxs-lookup"><span data-stu-id="d0fef-137">The CLR uses this value as a unique identifier for the stream.</span></span> <span data-ttu-id="d0fef-138">Ogni valore viene confrontato con i valori per `pAssemblyId` restituito da altre chiamate a `ProvideAssembly`.</span><span class="sxs-lookup"><span data-stu-id="d0fef-138">It checks each value against the values for `pAssemblyId` returned by other calls to `ProvideAssembly`.</span></span> <span data-ttu-id="d0fef-139">Se l'host restituisce lo stesso `pAssemblyId` valore per un altro `IStream`, Common Language Runtime controlla se il contenuto del flusso è già stato mappato.</span><span class="sxs-lookup"><span data-stu-id="d0fef-139">If the host returns the same `pAssemblyId` value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="d0fef-140">In questo caso, il runtime carica la copia esistente di immagine anziché eseguire il mapping di una nuova.</span><span class="sxs-lookup"><span data-stu-id="d0fef-140">If so, the runtime loads the existing copy of the image instead of mapping a new one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0fef-141">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d0fef-141">Requirements</span></span>  
 <span data-ttu-id="d0fef-142">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0fef-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0fef-143">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d0fef-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d0fef-144">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d0fef-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d0fef-145">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0fef-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0fef-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0fef-146">See also</span></span>

- [<span data-ttu-id="d0fef-147">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="d0fef-147">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="d0fef-148">Interfaccia IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="d0fef-148">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="d0fef-149">Interfaccia IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="d0fef-149">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)

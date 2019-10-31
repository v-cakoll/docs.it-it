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
ms.openlocfilehash: a93d700c9c398076d87156cd2eb9c6d0d08cccfd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124479"
---
# <a name="ihostassemblystoreprovideassembly-method"></a><span data-ttu-id="91d6e-102">Metodo IHostAssemblyStore::ProvideAssembly</span><span class="sxs-lookup"><span data-stu-id="91d6e-102">IHostAssemblyStore::ProvideAssembly Method</span></span>
<span data-ttu-id="91d6e-103">Ottiene un riferimento a un assembly a cui non viene fatto riferimento da [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) restituito da [IHostAssemblyManager:: GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span><span class="sxs-lookup"><span data-stu-id="91d6e-103">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that is returned from [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span> <span data-ttu-id="91d6e-104">Il Common Language Runtime (CLR) chiama `ProvideAssembly` per ogni assembly che non viene visualizzato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="91d6e-104">The common language runtime (CLR) calls `ProvideAssembly` for each assembly that does not appear in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91d6e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="91d6e-105">Syntax</span></span>  
  
```cpp  
HRESULT ProvideAssembly (  
    [in]  AssemblyBindInfo *pBindInfo,  
    [out] UINT64           *pAssemblyId,  
    [out] UINT64           *pHostContext,  
    [out] IStream          **ppStmAssemblyImage,  
    [out] IStream          **ppStmPDB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91d6e-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="91d6e-106">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="91d6e-107">in Puntatore a un'istanza di [AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) utilizzata dall'host per determinare determinate caratteristiche di associazione, inclusa la presenza o l'assenza di criteri di controllo delle versioni e l'assembly a cui eseguire l'associazione.</span><span class="sxs-lookup"><span data-stu-id="91d6e-107">[in] A pointer to an [AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) instance that the host uses to determine certain bind characteristics, including the presence or absence of any versioning policy, and which assembly to bind to.</span></span>  
  
 `pAssemblyId`  
 <span data-ttu-id="91d6e-108">out Puntatore a un identificatore univoco per l'assembly richiesto per questo `IStream`.</span><span class="sxs-lookup"><span data-stu-id="91d6e-108">[out] A pointer to a unique identifier for the requested assembly for this `IStream`.</span></span>  
  
 `pHostContext`  
 <span data-ttu-id="91d6e-109">out Puntatore a dati specifici dell'host utilizzati per determinare l'evidenza dell'assembly richiesto senza la necessità di una chiamata platform invoke.</span><span class="sxs-lookup"><span data-stu-id="91d6e-109">[out] A pointer to host-specific data that is used to determine the evidence of the requested assembly without the need of a platform invoke call.</span></span> <span data-ttu-id="91d6e-110">`pHostContext` corrisponde alla proprietà <xref:System.Reflection.Assembly.HostContext%2A> della classe <xref:System.Reflection.Assembly> gestita.</span><span class="sxs-lookup"><span data-stu-id="91d6e-110">`pHostContext` corresponds to the <xref:System.Reflection.Assembly.HostContext%2A> property of the managed <xref:System.Reflection.Assembly> class.</span></span>  
  
 `ppStmAssemblyImage`  
 <span data-ttu-id="91d6e-111">out Puntatore all'indirizzo di un `IStream` che contiene l'immagine del file eseguibile portabile (PE) da caricare o null se l'assembly non è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="91d6e-111">[out] A pointer to the address of an `IStream` that contains the portable executable (PE) image to be loaded, or null if the assembly could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="91d6e-112">out Puntatore all'indirizzo di un `IStream` contenente le informazioni di debug del programma (PDB) o null se il file con estensione PDB non è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="91d6e-112">[out] A pointer to the address of an `IStream` that contains the program debug (PDB) information, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="91d6e-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="91d6e-113">Return Value</span></span>  
  
|<span data-ttu-id="91d6e-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="91d6e-114">HRESULT</span></span>|<span data-ttu-id="91d6e-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91d6e-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="91d6e-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="91d6e-116">S_OK</span></span>|<span data-ttu-id="91d6e-117">`ProvideAssembly` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="91d6e-117">`ProvideAssembly` returned successfully.</span></span>|  
|<span data-ttu-id="91d6e-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="91d6e-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="91d6e-119">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="91d6e-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="91d6e-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="91d6e-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="91d6e-121">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="91d6e-121">The call timed out.</span></span>|  
|<span data-ttu-id="91d6e-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="91d6e-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="91d6e-123">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="91d6e-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="91d6e-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="91d6e-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="91d6e-125">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="91d6e-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="91d6e-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="91d6e-126">E_FAIL</span></span>|<span data-ttu-id="91d6e-127">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="91d6e-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="91d6e-128">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="91d6e-128">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="91d6e-129">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="91d6e-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="91d6e-130">COR_E_FILENOTFOUND (0x80070002)</span><span class="sxs-lookup"><span data-stu-id="91d6e-130">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="91d6e-131">Impossibile trovare l'assembly richiesto.</span><span class="sxs-lookup"><span data-stu-id="91d6e-131">The requested assembly could not be located.</span></span>|  
|<span data-ttu-id="91d6e-132">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="91d6e-132">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="91d6e-133">La dimensione del buffer specificata da `pAssemblyId` non è sufficiente per contenere l'identificatore che l'host vuole restituire.</span><span class="sxs-lookup"><span data-stu-id="91d6e-133">The buffer size specified by `pAssemblyId` is not large enough to hold the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91d6e-134">Note</span><span class="sxs-lookup"><span data-stu-id="91d6e-134">Remarks</span></span>  
 <span data-ttu-id="91d6e-135">Il valore Identity restituito per `pAssemblyId` viene specificato dall'host.</span><span class="sxs-lookup"><span data-stu-id="91d6e-135">The identity value returned for `pAssemblyId` is specified by the host.</span></span> <span data-ttu-id="91d6e-136">Gli identificatori devono essere univoci entro la durata di un processo.</span><span class="sxs-lookup"><span data-stu-id="91d6e-136">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="91d6e-137">CLR utilizza questo valore come identificatore univoco per il flusso.</span><span class="sxs-lookup"><span data-stu-id="91d6e-137">The CLR uses this value as a unique identifier for the stream.</span></span> <span data-ttu-id="91d6e-138">Controlla ogni valore in base ai valori per `pAssemblyId` restituiti da altre chiamate al `ProvideAssembly`.</span><span class="sxs-lookup"><span data-stu-id="91d6e-138">It checks each value against the values for `pAssemblyId` returned by other calls to `ProvideAssembly`.</span></span> <span data-ttu-id="91d6e-139">Se l'host restituisce lo stesso valore di `pAssemblyId` per un'altra `IStream`, CLR verifica se è già stato eseguito il mapping del contenuto del flusso.</span><span class="sxs-lookup"><span data-stu-id="91d6e-139">If the host returns the same `pAssemblyId` value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="91d6e-140">In tal caso, il runtime carica la copia esistente dell'immagine anziché mapparne una nuova.</span><span class="sxs-lookup"><span data-stu-id="91d6e-140">If so, the runtime loads the existing copy of the image instead of mapping a new one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91d6e-141">Requisiti</span><span class="sxs-lookup"><span data-stu-id="91d6e-141">Requirements</span></span>  
 <span data-ttu-id="91d6e-142">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91d6e-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91d6e-143">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="91d6e-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="91d6e-144">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="91d6e-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="91d6e-145">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91d6e-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91d6e-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91d6e-146">See also</span></span>

- [<span data-ttu-id="91d6e-147">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="91d6e-147">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="91d6e-148">Interfaccia IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="91d6e-148">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="91d6e-149">Interfaccia IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="91d6e-149">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)

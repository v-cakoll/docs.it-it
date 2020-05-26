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
ms.openlocfilehash: 002f4177f19c2aae99e91e3fe1029b81e17481dc
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805005"
---
# <a name="ihostassemblystoreprovidemodule-method"></a><span data-ttu-id="bd644-102">Metodo IHostAssemblyStore::ProvideModule</span><span class="sxs-lookup"><span data-stu-id="bd644-102">IHostAssemblyStore::ProvideModule Method</span></span>
<span data-ttu-id="bd644-103">Risolve un modulo all'interno di un assembly o di un file di risorse collegato, ma non incorporato.</span><span class="sxs-lookup"><span data-stu-id="bd644-103">Resolves a module within an assembly or a linked (but not an embedded) resource file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd644-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bd644-104">Syntax</span></span>  
  
```cpp  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd644-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bd644-105">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="bd644-106">in Puntatore a un'istanza di [ModuleBindInfo](modulebindinfo-structure.md) che descrive il modulo, l' <xref:System.AppDomain> assembly e il nome del modulo richiesti.</span><span class="sxs-lookup"><span data-stu-id="bd644-106">[in] A pointer to a [ModuleBindInfo](modulebindinfo-structure.md) instance that describes the requested module's <xref:System.AppDomain>, assembly, and module name.</span></span>  
  
 `pdwModuleId`  
 <span data-ttu-id="bd644-107">out Puntatore a un identificatore univoco per l'oggetto `IStream` che contiene il modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="bd644-107">[out] A pointer to a unique identifier for the `IStream` containing the loaded module.</span></span>  
  
 `ppStmModuleImage`  
 <span data-ttu-id="bd644-108">out Puntatore all'indirizzo di un `IStream` oggetto che contiene l'immagine del file eseguibile di tipo PE da caricare oppure null se il modulo non è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="bd644-108">[out] A pointer to the address of an `IStream` object, which contains the portable executable (PE) image to be loaded, or null if the module could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="bd644-109">out Puntatore all'indirizzo di un `IStream` oggetto che contiene le informazioni di debug del programma (PDB) per il modulo richiesto oppure null se il file con estensione PDB non è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="bd644-109">[out] A pointer to the address of an `IStream` object, which contains the program debug (PDB) information for the requested module, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bd644-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bd644-110">Return Value</span></span>  
  
|<span data-ttu-id="bd644-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bd644-111">HRESULT</span></span>|<span data-ttu-id="bd644-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bd644-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bd644-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="bd644-113">S_OK</span></span>|<span data-ttu-id="bd644-114">`ProvideModule`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="bd644-114">`ProvideModule` returned successfully.</span></span>|  
|<span data-ttu-id="bd644-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bd644-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bd644-116">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="bd644-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bd644-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bd644-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bd644-118">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="bd644-118">The call timed out.</span></span>|  
|<span data-ttu-id="bd644-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bd644-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bd644-120">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="bd644-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bd644-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bd644-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bd644-122">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="bd644-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bd644-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bd644-123">E_FAIL</span></span>|<span data-ttu-id="bd644-124">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="bd644-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bd644-125">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="bd644-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bd644-126">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="bd644-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="bd644-127">COR_E_FILENOTFOUND (0x80070002)</span><span class="sxs-lookup"><span data-stu-id="bd644-127">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="bd644-128">Impossibile trovare l'assembly o la risorsa collegata richiesta.</span><span class="sxs-lookup"><span data-stu-id="bd644-128">The requested assembly or linked resource could not be located.</span></span>|  
|<span data-ttu-id="bd644-129">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="bd644-129">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="bd644-130">`pdwModuleId`non è sufficientemente grande da contenere l'identificatore che l'host vuole restituire.</span><span class="sxs-lookup"><span data-stu-id="bd644-130">`pdwModuleId` is not large enough to contain the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd644-131">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="bd644-131">Remarks</span></span>  
 <span data-ttu-id="bd644-132">Il valore Identity restituito per `pdwModuleId` viene specificato dall'host.</span><span class="sxs-lookup"><span data-stu-id="bd644-132">The identity value returned for `pdwModuleId` is specified by the host.</span></span> <span data-ttu-id="bd644-133">Gli identificatori devono essere univoci entro la durata di un processo.</span><span class="sxs-lookup"><span data-stu-id="bd644-133">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="bd644-134">CLR utilizza questo valore come identificatore univoco per il flusso associato.</span><span class="sxs-lookup"><span data-stu-id="bd644-134">The CLR uses this value as the unique identifier for the associated stream.</span></span> <span data-ttu-id="bd644-135">Verifica ogni valore rispetto ai valori `pAssemblyId` restituiti dalle chiamate a [ProvideAssembly](ihostassemblystore-provideassembly-method.md) e ai valori `pdwModuleId` restituiti da altre chiamate a `ProvideModule` .</span><span class="sxs-lookup"><span data-stu-id="bd644-135">It checks each value against the values for `pAssemblyId` returned by calls to [ProvideAssembly](ihostassemblystore-provideassembly-method.md) and against the values for `pdwModuleId` returned by other calls to `ProvideModule`.</span></span> <span data-ttu-id="bd644-136">Se l'host restituisce lo stesso valore di identificatore per un altro `IStream` , CLR verifica se il contenuto del flusso è già stato mappato.</span><span class="sxs-lookup"><span data-stu-id="bd644-136">If the host returns the same identifier value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="bd644-137">In tal caso, CLR carica la copia esistente dell'immagine anziché mapparne una nuova.</span><span class="sxs-lookup"><span data-stu-id="bd644-137">If so, the CLR loads the existing copy of the image instead of mapping a new one.</span></span> <span data-ttu-id="bd644-138">Pertanto, anche l'identificatore non deve sovrapporsi agli identificatori di assembly restituiti da `ProvideAssembly` .</span><span class="sxs-lookup"><span data-stu-id="bd644-138">Therefore, the identifier must also not overlap with the assembly identifiers returned from `ProvideAssembly`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd644-139">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bd644-139">Requirements</span></span>  
 <span data-ttu-id="bd644-140">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd644-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd644-141">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="bd644-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bd644-142">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="bd644-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bd644-143">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd644-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd644-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd644-144">See also</span></span>

- [<span data-ttu-id="bd644-145">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="bd644-145">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="bd644-146">Interfaccia IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="bd644-146">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="bd644-147">Interfaccia IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="bd644-147">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)

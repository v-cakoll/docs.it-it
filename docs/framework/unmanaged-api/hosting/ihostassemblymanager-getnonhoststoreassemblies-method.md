---
title: Metodo IHostAssemblyManager::GetNonHostStoreAssemblies
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager.GetNonHostStoreAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies
helpviewer_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies method [.NET Framework hosting]
- GetNonHostStoreAssemblies method [.NET Framework hosting]
ms.assetid: d2250b38-c76a-40ce-80c8-ba45149886e8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3680721c70ab69776c973913d929f7bdd9db3909
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779451"
---
# <a name="ihostassemblymanagergetnonhoststoreassemblies-method"></a><span data-ttu-id="312f2-102">Metodo IHostAssemblyManager::GetNonHostStoreAssemblies</span><span class="sxs-lookup"><span data-stu-id="312f2-102">IHostAssemblyManager::GetNonHostStoreAssemblies Method</span></span>
<span data-ttu-id="312f2-103">Ottiene un puntatore a interfaccia a un [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) che rappresenta l'elenco di assembly a cui l'host si aspetta che common language runtime (CLR) da caricare.</span><span class="sxs-lookup"><span data-stu-id="312f2-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the common language runtime (CLR) to load.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="312f2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="312f2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNonHostStoreAssemblies (  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="312f2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="312f2-105">Parameters</span></span>  
 `ppReferenceList`  
 <span data-ttu-id="312f2-106">[out] Un puntatore all'indirizzo di un `ICLRAssemblyReferenceList` che contiene un elenco di riferimenti ad assembly CLR da caricare previsti dall'host.</span><span class="sxs-lookup"><span data-stu-id="312f2-106">[out] A pointer to the address of an `ICLRAssemblyReferenceList` that contains a list of references to assemblies that the host expects the CLR to load.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="312f2-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="312f2-107">Return Value</span></span>  
  
|<span data-ttu-id="312f2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="312f2-108">HRESULT</span></span>|<span data-ttu-id="312f2-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="312f2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="312f2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="312f2-110">S_OK</span></span>|<span data-ttu-id="312f2-111">`GetNonHostStoreAssemblies` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="312f2-111">`GetNonHostStoreAssemblies` returned successfully.</span></span>|  
|<span data-ttu-id="312f2-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="312f2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="312f2-113">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="312f2-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="312f2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="312f2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="312f2-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="312f2-115">The call timed out.</span></span>|  
|<span data-ttu-id="312f2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="312f2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="312f2-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="312f2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="312f2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="312f2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="312f2-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="312f2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="312f2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="312f2-120">E_FAIL</span></span>|<span data-ttu-id="312f2-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="312f2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="312f2-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="312f2-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="312f2-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="312f2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="312f2-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="312f2-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="312f2-125">Memoria insufficiente era disponibile per creare l'elenco di riferimenti per la richiesta `ICLRAssemblyReferenceList`.</span><span class="sxs-lookup"><span data-stu-id="312f2-125">Not enough memory was available to create the list of references for the requested `ICLRAssemblyReferenceList`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="312f2-126">Note</span><span class="sxs-lookup"><span data-stu-id="312f2-126">Remarks</span></span>  
 <span data-ttu-id="312f2-127">CLR risolve i riferimenti utilizzando il set di linee guida seguente:</span><span class="sxs-lookup"><span data-stu-id="312f2-127">The CLR resolves references using the following set of guidelines:</span></span>  
  
- <span data-ttu-id="312f2-128">In primo luogo, consulta l'elenco di riferimenti ad assembly restituito da `GetNonHostStoreAssemblies`.</span><span class="sxs-lookup"><span data-stu-id="312f2-128">First, it consults the list of assembly references returned by `GetNonHostStoreAssemblies`.</span></span>  
  
- <span data-ttu-id="312f2-129">Se l'assembly viene visualizzato nell'elenco, CLR viene associata normalmente a esso.</span><span class="sxs-lookup"><span data-stu-id="312f2-129">If the assembly appears in the list, the CLR binds to it normally.</span></span>  
  
- <span data-ttu-id="312f2-130">Se l'assembly non vengono visualizzati nell'elenco e l'host ha fornito un'implementazione di [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), CLR chiama [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) per consentire all'host di fornire il assembly a cui associarsi.</span><span class="sxs-lookup"><span data-stu-id="312f2-130">If the assembly does not appear in the list and the host has provided an implementation of [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), the CLR calls [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) to allow the host to supply the assembly to bind to.</span></span>  
  
- <span data-ttu-id="312f2-131">In caso contrario, CLR non riesce a eseguire l'associazione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="312f2-131">Otherwise, the CLR fails to bind to the assembly.</span></span>  
  
 <span data-ttu-id="312f2-132">Se l'host imposta `ppReferenceList` su null, il CLR esamina innanzitutto la global assembly cache, chiama `ProvideAssembly`e quindi i probe di base dell'applicazione per risolvere un riferimento all'assembly.</span><span class="sxs-lookup"><span data-stu-id="312f2-132">If the host sets `ppReferenceList` to null, the CLR first probes the global assembly cache, calls `ProvideAssembly`, and then probes the application base to resolve an assembly reference.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="312f2-133">Al momento dell'inizializzazione, CLR chiama `GetNonHostStoreAssemblies` una sola volta.</span><span class="sxs-lookup"><span data-stu-id="312f2-133">Upon initialization, the CLR calls `GetNonHostStoreAssemblies` only once.</span></span> <span data-ttu-id="312f2-134">Il metodo non viene chiamato nuovamente.</span><span class="sxs-lookup"><span data-stu-id="312f2-134">The method is not called again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="312f2-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="312f2-135">Requirements</span></span>  
 <span data-ttu-id="312f2-136">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="312f2-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="312f2-137">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="312f2-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="312f2-138">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="312f2-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="312f2-139">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="312f2-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="312f2-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="312f2-140">See also</span></span>

- [<span data-ttu-id="312f2-141">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="312f2-141">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="312f2-142">Interfaccia IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="312f2-142">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="312f2-143">Interfaccia IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="312f2-143">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)

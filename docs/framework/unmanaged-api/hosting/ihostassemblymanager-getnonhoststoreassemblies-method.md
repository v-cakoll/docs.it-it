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
ms.openlocfilehash: 0dc2f625da7f4e37583f198c8d6dba86f6dcdb10
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805060"
---
# <a name="ihostassemblymanagergetnonhoststoreassemblies-method"></a><span data-ttu-id="e96f4-102">Metodo IHostAssemblyManager::GetNonHostStoreAssemblies</span><span class="sxs-lookup"><span data-stu-id="e96f4-102">IHostAssemblyManager::GetNonHostStoreAssemblies Method</span></span>
<span data-ttu-id="e96f4-103">Ottiene un puntatore a interfaccia a un [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) che rappresenta l'elenco di assembly che l'host prevede venga caricato dal Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="e96f4-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the common language runtime (CLR) to load.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e96f4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e96f4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNonHostStoreAssemblies (  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e96f4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e96f4-105">Parameters</span></span>  
 `ppReferenceList`  
 <span data-ttu-id="e96f4-106">out Puntatore all'indirizzo di un oggetto `ICLRAssemblyReferenceList` che contiene un elenco di riferimenti agli assembly che l'host prevede venga caricato da CLR.</span><span class="sxs-lookup"><span data-stu-id="e96f4-106">[out] A pointer to the address of an `ICLRAssemblyReferenceList` that contains a list of references to assemblies that the host expects the CLR to load.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e96f4-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e96f4-107">Return Value</span></span>  
  
|<span data-ttu-id="e96f4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e96f4-108">HRESULT</span></span>|<span data-ttu-id="e96f4-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e96f4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e96f4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e96f4-110">S_OK</span></span>|<span data-ttu-id="e96f4-111">`GetNonHostStoreAssemblies`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="e96f4-111">`GetNonHostStoreAssemblies` returned successfully.</span></span>|  
|<span data-ttu-id="e96f4-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e96f4-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e96f4-113">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="e96f4-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e96f4-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e96f4-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e96f4-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="e96f4-115">The call timed out.</span></span>|  
|<span data-ttu-id="e96f4-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e96f4-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e96f4-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="e96f4-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e96f4-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e96f4-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e96f4-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="e96f4-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e96f4-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e96f4-120">E_FAIL</span></span>|<span data-ttu-id="e96f4-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="e96f4-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e96f4-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="e96f4-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e96f4-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e96f4-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e96f4-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="e96f4-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="e96f4-125">Memoria insufficiente per creare l'elenco di riferimenti per la richiesta `ICLRAssemblyReferenceList` .</span><span class="sxs-lookup"><span data-stu-id="e96f4-125">Not enough memory was available to create the list of references for the requested `ICLRAssemblyReferenceList`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e96f4-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e96f4-126">Remarks</span></span>  
 <span data-ttu-id="e96f4-127">CLR risolve i riferimenti usando il set di linee guida seguente:</span><span class="sxs-lookup"><span data-stu-id="e96f4-127">The CLR resolves references using the following set of guidelines:</span></span>  
  
- <span data-ttu-id="e96f4-128">In primo luogo, consulta l'elenco di riferimenti ad assembly restituiti da `GetNonHostStoreAssemblies` .</span><span class="sxs-lookup"><span data-stu-id="e96f4-128">First, it consults the list of assembly references returned by `GetNonHostStoreAssemblies`.</span></span>  
  
- <span data-ttu-id="e96f4-129">Se l'assembly viene visualizzato nell'elenco, il CLR viene associato normalmente a tale assembly.</span><span class="sxs-lookup"><span data-stu-id="e96f4-129">If the assembly appears in the list, the CLR binds to it normally.</span></span>  
  
- <span data-ttu-id="e96f4-130">Se l'assembly non è presente nell'elenco e l'host ha fornito un'implementazione di [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), CLR chiama [IHostAssemblyStore::P rovideassembly](ihostassemblystore-provideassembly-method.md) per consentire all'host di fornire l'assembly a cui eseguire l'associazione.</span><span class="sxs-lookup"><span data-stu-id="e96f4-130">If the assembly does not appear in the list and the host has provided an implementation of [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), the CLR calls [IHostAssemblyStore::ProvideAssembly](ihostassemblystore-provideassembly-method.md) to allow the host to supply the assembly to bind to.</span></span>  
  
- <span data-ttu-id="e96f4-131">In caso contrario, CLR non è in grado di eseguire il binding all'assembly.</span><span class="sxs-lookup"><span data-stu-id="e96f4-131">Otherwise, the CLR fails to bind to the assembly.</span></span>  
  
 <span data-ttu-id="e96f4-132">Se l'host imposta `ppReferenceList` su null, CLR verifica prima di tutto la Global assembly cache, chiama `ProvideAssembly` e quindi esegue il probe della base dell'applicazione per risolvere un riferimento a un assembly.</span><span class="sxs-lookup"><span data-stu-id="e96f4-132">If the host sets `ppReferenceList` to null, the CLR first probes the global assembly cache, calls `ProvideAssembly`, and then probes the application base to resolve an assembly reference.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e96f4-133">Durante l'inizializzazione, CLR chiama `GetNonHostStoreAssemblies` una sola volta.</span><span class="sxs-lookup"><span data-stu-id="e96f4-133">Upon initialization, the CLR calls `GetNonHostStoreAssemblies` only once.</span></span> <span data-ttu-id="e96f4-134">Il metodo non viene chiamato nuovamente.</span><span class="sxs-lookup"><span data-stu-id="e96f4-134">The method is not called again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e96f4-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e96f4-135">Requirements</span></span>  
 <span data-ttu-id="e96f4-136">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e96f4-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e96f4-137">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e96f4-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e96f4-138">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e96f4-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e96f4-139">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e96f4-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e96f4-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e96f4-140">See also</span></span>

- [<span data-ttu-id="e96f4-141">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="e96f4-141">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="e96f4-142">Interfaccia IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="e96f4-142">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="e96f4-143">Interfaccia IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="e96f4-143">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)

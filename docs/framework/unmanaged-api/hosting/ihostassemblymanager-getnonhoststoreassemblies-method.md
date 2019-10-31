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
ms.openlocfilehash: eb715e1a4f9a210a1440874a9a8cea2d85345d33
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124571"
---
# <a name="ihostassemblymanagergetnonhoststoreassemblies-method"></a><span data-ttu-id="561c0-102">Metodo IHostAssemblyManager::GetNonHostStoreAssemblies</span><span class="sxs-lookup"><span data-stu-id="561c0-102">IHostAssemblyManager::GetNonHostStoreAssemblies Method</span></span>
<span data-ttu-id="561c0-103">Ottiene un puntatore a interfaccia a un [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) che rappresenta l'elenco di assembly che l'host prevede venga caricato dal Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="561c0-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the common language runtime (CLR) to load.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="561c0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="561c0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNonHostStoreAssemblies (  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="561c0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="561c0-105">Parameters</span></span>  
 `ppReferenceList`  
 <span data-ttu-id="561c0-106">out Puntatore all'indirizzo di un `ICLRAssemblyReferenceList` contenente un elenco di riferimenti agli assembly che l'host prevede venga caricato da CLR.</span><span class="sxs-lookup"><span data-stu-id="561c0-106">[out] A pointer to the address of an `ICLRAssemblyReferenceList` that contains a list of references to assemblies that the host expects the CLR to load.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="561c0-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="561c0-107">Return Value</span></span>  
  
|<span data-ttu-id="561c0-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="561c0-108">HRESULT</span></span>|<span data-ttu-id="561c0-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="561c0-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="561c0-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="561c0-110">S_OK</span></span>|<span data-ttu-id="561c0-111">`GetNonHostStoreAssemblies` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="561c0-111">`GetNonHostStoreAssemblies` returned successfully.</span></span>|  
|<span data-ttu-id="561c0-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="561c0-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="561c0-113">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="561c0-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="561c0-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="561c0-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="561c0-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="561c0-115">The call timed out.</span></span>|  
|<span data-ttu-id="561c0-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="561c0-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="561c0-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="561c0-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="561c0-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="561c0-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="561c0-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="561c0-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="561c0-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="561c0-120">E_FAIL</span></span>|<span data-ttu-id="561c0-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="561c0-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="561c0-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="561c0-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="561c0-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="561c0-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="561c0-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="561c0-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="561c0-125">Memoria insufficiente per creare l'elenco di riferimenti per la `ICLRAssemblyReferenceList`richiesta.</span><span class="sxs-lookup"><span data-stu-id="561c0-125">Not enough memory was available to create the list of references for the requested `ICLRAssemblyReferenceList`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="561c0-126">Note</span><span class="sxs-lookup"><span data-stu-id="561c0-126">Remarks</span></span>  
 <span data-ttu-id="561c0-127">CLR risolve i riferimenti usando il set di linee guida seguente:</span><span class="sxs-lookup"><span data-stu-id="561c0-127">The CLR resolves references using the following set of guidelines:</span></span>  
  
- <span data-ttu-id="561c0-128">In primo luogo, consulta l'elenco di riferimenti ad assembly restituiti da `GetNonHostStoreAssemblies`.</span><span class="sxs-lookup"><span data-stu-id="561c0-128">First, it consults the list of assembly references returned by `GetNonHostStoreAssemblies`.</span></span>  
  
- <span data-ttu-id="561c0-129">Se l'assembly viene visualizzato nell'elenco, il CLR viene associato normalmente a tale assembly.</span><span class="sxs-lookup"><span data-stu-id="561c0-129">If the assembly appears in the list, the CLR binds to it normally.</span></span>  
  
- <span data-ttu-id="561c0-130">Se l'assembly non è presente nell'elenco e l'host ha fornito un'implementazione di [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), CLR chiama [IHostAssemblyStore::P rovideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) per consentire all'host di fornire l'assembly a cui eseguire l'associazione.</span><span class="sxs-lookup"><span data-stu-id="561c0-130">If the assembly does not appear in the list and the host has provided an implementation of [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), the CLR calls [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) to allow the host to supply the assembly to bind to.</span></span>  
  
- <span data-ttu-id="561c0-131">In caso contrario, CLR non è in grado di eseguire il binding all'assembly.</span><span class="sxs-lookup"><span data-stu-id="561c0-131">Otherwise, the CLR fails to bind to the assembly.</span></span>  
  
 <span data-ttu-id="561c0-132">Se l'host imposta `ppReferenceList` su null, CLR verifica prima di tutto la Global Assembly Cache, chiama `ProvideAssembly`, quindi esegue il probe della base dell'applicazione per risolvere un riferimento a un assembly.</span><span class="sxs-lookup"><span data-stu-id="561c0-132">If the host sets `ppReferenceList` to null, the CLR first probes the global assembly cache, calls `ProvideAssembly`, and then probes the application base to resolve an assembly reference.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="561c0-133">Durante l'inizializzazione, CLR chiama `GetNonHostStoreAssemblies` una sola volta.</span><span class="sxs-lookup"><span data-stu-id="561c0-133">Upon initialization, the CLR calls `GetNonHostStoreAssemblies` only once.</span></span> <span data-ttu-id="561c0-134">Il metodo non viene chiamato nuovamente.</span><span class="sxs-lookup"><span data-stu-id="561c0-134">The method is not called again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="561c0-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="561c0-135">Requirements</span></span>  
 <span data-ttu-id="561c0-136">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="561c0-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="561c0-137">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="561c0-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="561c0-138">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="561c0-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="561c0-139">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="561c0-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="561c0-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="561c0-140">See also</span></span>

- [<span data-ttu-id="561c0-141">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="561c0-141">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="561c0-142">Interfaccia IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="561c0-142">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="561c0-143">Interfaccia IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="561c0-143">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)

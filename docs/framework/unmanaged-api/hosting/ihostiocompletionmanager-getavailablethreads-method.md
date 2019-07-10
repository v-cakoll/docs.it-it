---
title: Metodo IHostIoCompletionManager::GetAvailableThreads
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: bab363d1-b859-47a4-9884-5661c611cce7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4316412cec26ae5698918ff65b2da65de9f36ff2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779621"
---
# <a name="ihostiocompletionmanagergetavailablethreads-method"></a><span data-ttu-id="508c4-102">Metodo IHostIoCompletionManager::GetAvailableThreads</span><span class="sxs-lookup"><span data-stu-id="508c4-102">IHostIoCompletionManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="508c4-103">Ottiene il numero di thread di completamento i/o, del numero totale di thread gestiti dall'host, che non stanno elaborando le richieste.</span><span class="sxs-lookup"><span data-stu-id="508c4-103">Gets the number of I/O completion threads, of the total number of threads managed by the host, that are not currently servicing requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="508c4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="508c4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="508c4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="508c4-105">Parameters</span></span>  
 `pdwAvailableIoCompletionThreads`  
 <span data-ttu-id="508c4-106">[out] Puntatore al numero di thread di completamento i/o gestito dall'host che sono attualmente disponibili per soddisfare le richieste.</span><span class="sxs-lookup"><span data-stu-id="508c4-106">[out] A pointer to the number of I/O completion threads managed by the host that are currently available to service requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="508c4-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="508c4-107">Return Value</span></span>  
  
|<span data-ttu-id="508c4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="508c4-108">HRESULT</span></span>|<span data-ttu-id="508c4-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="508c4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="508c4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="508c4-110">S_OK</span></span>|<span data-ttu-id="508c4-111">`GetAvailableThreads` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="508c4-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="508c4-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="508c4-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="508c4-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="508c4-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="508c4-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="508c4-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="508c4-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="508c4-115">The call timed out.</span></span>|  
|<span data-ttu-id="508c4-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="508c4-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="508c4-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="508c4-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="508c4-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="508c4-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="508c4-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="508c4-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="508c4-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="508c4-120">E_FAIL</span></span>|<span data-ttu-id="508c4-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="508c4-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="508c4-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="508c4-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="508c4-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="508c4-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="508c4-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="508c4-124">E_NOTIMPL</span></span>|<span data-ttu-id="508c4-125">L'host non fornisce un'implementazione di `GetAvailableThreads`.</span><span class="sxs-lookup"><span data-stu-id="508c4-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="508c4-126">Note</span><span class="sxs-lookup"><span data-stu-id="508c4-126">Remarks</span></span>  
 <span data-ttu-id="508c4-127">Un host potrebbe essere necessario il controllo esclusivo rispetto alla dimensione del pool di thread di completamento i/o, per motivi, ad esempio la scalabilità, prestazioni o implementazione.</span><span class="sxs-lookup"><span data-stu-id="508c4-127">A host might want exclusive control over the size of the I/O completion thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="508c4-128">Pertanto, l'host non è necessario implementare `GetAvailableThreads`.</span><span class="sxs-lookup"><span data-stu-id="508c4-128">Therefore, the host is not required to implement `GetAvailableThreads`.</span></span> <span data-ttu-id="508c4-129">In questo caso, l'host deve restituire E_NOTIMPL da questo metodo.</span><span class="sxs-lookup"><span data-stu-id="508c4-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="508c4-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="508c4-130">Requirements</span></span>  
 <span data-ttu-id="508c4-131">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="508c4-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="508c4-132">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="508c4-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="508c4-133">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="508c4-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="508c4-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="508c4-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="508c4-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="508c4-135">See also</span></span>

- [<span data-ttu-id="508c4-136">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="508c4-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="508c4-137">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="508c4-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)

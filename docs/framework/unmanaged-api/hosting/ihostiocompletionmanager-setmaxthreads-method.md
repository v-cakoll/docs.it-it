---
title: Metodo IHostIoCompletionManager::SetMaxThreads
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetMaxThreads
helpviewer_keywords:
- IHostIoCompletionManager::SetMaxThreads method [.NET Framework hosting]
- SetMaxThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: ebad4f40-d9f1-4dc6-9b27-a89c9eb3926f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 345c7b88b6967773a185538943591383a686748c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224123"
---
# <a name="ihostiocompletionmanagersetmaxthreads-method"></a><span data-ttu-id="19793-102">Metodo IHostIoCompletionManager::SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="19793-102">IHostIoCompletionManager::SetMaxThreads Method</span></span>
<span data-ttu-id="19793-103">Imposta il numero massimo di thread che l'host assegnati per soddisfare le richieste dei / o.</span><span class="sxs-lookup"><span data-stu-id="19793-103">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19793-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="19793-104">Syntax</span></span>  
  
```  
HRESULT SetMaxThreads (  
    [in] DWORD dwMaxIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19793-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="19793-105">Parameters</span></span>  
 `dwMaxIoCompletionThreads`  
 <span data-ttu-id="19793-106">[in] Il numero massimo di thread da allocare per le richieste dei / o.</span><span class="sxs-lookup"><span data-stu-id="19793-106">[in] The maximum number of threads to allot for I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="19793-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="19793-107">Return Value</span></span>  
  
|<span data-ttu-id="19793-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="19793-108">HRESULT</span></span>|<span data-ttu-id="19793-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="19793-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="19793-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="19793-110">S_OK</span></span>|`SetMaxThreads` <span data-ttu-id="19793-111">stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="19793-111">returned successfully.</span></span>|  
|<span data-ttu-id="19793-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="19793-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="19793-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="19793-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="19793-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="19793-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="19793-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="19793-115">The call timed out.</span></span>|  
|<span data-ttu-id="19793-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="19793-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="19793-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="19793-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="19793-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="19793-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="19793-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="19793-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="19793-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="19793-120">E_FAIL</span></span>|<span data-ttu-id="19793-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="19793-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="19793-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="19793-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="19793-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="19793-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="19793-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="19793-124">E_NOTIMPL</span></span>|<span data-ttu-id="19793-125">L'host non fornisce un'implementazione di `SetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="19793-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19793-126">Note</span><span class="sxs-lookup"><span data-stu-id="19793-126">Remarks</span></span>  
 `SetMaxThreads` <span data-ttu-id="19793-127">fornisce Common Language Runtime con la possibilità di impostare il numero massimo di thread che sono disponibili per soddisfare le richieste sulle porte i/o.</span><span class="sxs-lookup"><span data-stu-id="19793-127">provides the CLR with an opportunity to set the maximum number of threads that are available to service requests on I/O ports.</span></span> <span data-ttu-id="19793-128">Un host potrebbe essere necessario il controllo esclusivo rispetto alla dimensione del pool di thread, per motivi, ad esempio la scalabilità, prestazioni o implementazione.</span><span class="sxs-lookup"><span data-stu-id="19793-128">A host might need exclusive control over the size of the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="19793-129">Per questo motivo, l'host non è necessaria per implementare `SetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="19793-129">For this reason, the host is not required to implement `SetMaxThreads`.</span></span> <span data-ttu-id="19793-130">In questo caso, un host deve restituire E_NOTIMPL da questo metodo.</span><span class="sxs-lookup"><span data-stu-id="19793-130">In this case, a host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19793-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="19793-131">Requirements</span></span>  
 <span data-ttu-id="19793-132">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19793-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19793-133">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="19793-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="19793-134">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="19793-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="19793-135">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="19793-135">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="19793-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19793-136">See also</span></span>

- [<span data-ttu-id="19793-137">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="19793-137">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="19793-138">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="19793-138">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)

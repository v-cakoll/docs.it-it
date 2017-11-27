---
title: Metodo IHostIoCompletionManager::GetAvailableThreads
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.GetAvailableThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: bab363d1-b859-47a4-9884-5661c611cce7
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f06e9fe0d07258fca107413d9ad328329b5456b6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostiocompletionmanagergetavailablethreads-method"></a><span data-ttu-id="b9153-102">Metodo IHostIoCompletionManager::GetAvailableThreads</span><span class="sxs-lookup"><span data-stu-id="b9153-102">IHostIoCompletionManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="b9153-103">Ottiene il numero di thread di completamento i/o, del numero totale di thread gestiti dall'host, che non sono attualmente rispondendo alle richieste.</span><span class="sxs-lookup"><span data-stu-id="b9153-103">Gets the number of I/O completion threads, of the total number of threads managed by the host, that are not currently servicing requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9153-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b9153-104">Syntax</span></span>  
  
```  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableIoCompletionThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9153-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b9153-105">Parameters</span></span>  
 `pdwAvailableIoCompletionThreads`  
 <span data-ttu-id="b9153-106">[out] Puntatore al numero di thread di completamento i/o gestiti dall'host sono attualmente disponibili per le richieste di servizio.</span><span class="sxs-lookup"><span data-stu-id="b9153-106">[out] A pointer to the number of I/O completion threads managed by the host that are currently available to service requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9153-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b9153-107">Return Value</span></span>  
  
|<span data-ttu-id="b9153-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b9153-108">HRESULT</span></span>|<span data-ttu-id="b9153-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b9153-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b9153-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b9153-110">S_OK</span></span>|<span data-ttu-id="b9153-111">`GetAvailableThreads`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="b9153-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="b9153-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b9153-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b9153-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b9153-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b9153-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b9153-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b9153-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b9153-115">The call timed out.</span></span>|  
|<span data-ttu-id="b9153-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b9153-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b9153-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="b9153-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b9153-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b9153-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b9153-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="b9153-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b9153-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b9153-120">E_FAIL</span></span>|<span data-ttu-id="b9153-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="b9153-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b9153-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="b9153-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b9153-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b9153-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b9153-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="b9153-124">E_NOTIMPL</span></span>|<span data-ttu-id="b9153-125">L'host non fornisce un'implementazione di `GetAvailableThreads`.</span><span class="sxs-lookup"><span data-stu-id="b9153-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9153-126">Note</span><span class="sxs-lookup"><span data-stu-id="b9153-126">Remarks</span></span>  
 <span data-ttu-id="b9153-127">Un host potrebbe richiedere il controllo esclusivo sulla dimensione del pool di thread di completamento i/o, per motivi di implementazione, prestazioni o scalabilità.</span><span class="sxs-lookup"><span data-stu-id="b9153-127">A host might want exclusive control over the size of the I/O completion thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="b9153-128">Pertanto, l'host non è necessario implementare `GetAvailableThreads`.</span><span class="sxs-lookup"><span data-stu-id="b9153-128">Therefore, the host is not required to implement `GetAvailableThreads`.</span></span> <span data-ttu-id="b9153-129">In questo caso, l'host deve restituire E_NOTIMPL da questo metodo.</span><span class="sxs-lookup"><span data-stu-id="b9153-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9153-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b9153-130">Requirements</span></span>  
 <span data-ttu-id="b9153-131">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9153-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9153-132">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="b9153-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b9153-133">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b9153-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b9153-134">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9153-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9153-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9153-135">See Also</span></span>  
 [<span data-ttu-id="b9153-136">ICLRIoCompletionManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="b9153-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="b9153-137">IHostIoCompletionManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="b9153-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)

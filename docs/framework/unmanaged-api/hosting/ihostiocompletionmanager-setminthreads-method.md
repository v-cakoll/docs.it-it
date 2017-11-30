---
title: Metodo IHostIoCompletionManager::SetMinThreads
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.SetMinThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: dea34b81-8d2b-4cc3-8696-0ad4291d8a92
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a8903aa2f2119ad3c4dceebfaba9ede26200e899
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostiocompletionmanagersetminthreads-method"></a><span data-ttu-id="a9209-102">Metodo IHostIoCompletionManager::SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="a9209-102">IHostIoCompletionManager::SetMinThreads Method</span></span>
<span data-ttu-id="a9209-103">Imposta il numero minimo di thread che l'host deve assegnare fino al completamento dei / o.</span><span class="sxs-lookup"><span data-stu-id="a9209-103">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9209-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a9209-104">Syntax</span></span>  
  
```  
HRESULT SetMinThreads (  
    [in] DWORD dwMinIoCompletionThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a9209-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a9209-105">Parameters</span></span>  
 `dwMinIoCompletionThreads`  
 <span data-ttu-id="a9209-106">[in] Il numero minimo di thread di completamento i/o che l'host deve creare.</span><span class="sxs-lookup"><span data-stu-id="a9209-106">[in] The minimum number of I/O completion threads that the host should create.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a9209-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a9209-107">Return Value</span></span>  
  
|<span data-ttu-id="a9209-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a9209-108">HRESULT</span></span>|<span data-ttu-id="a9209-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a9209-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a9209-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a9209-110">S_OK</span></span>|<span data-ttu-id="a9209-111">`SetMinThreads`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="a9209-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="a9209-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a9209-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a9209-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="a9209-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a9209-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a9209-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a9209-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="a9209-115">The call timed out.</span></span>|  
|<span data-ttu-id="a9209-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a9209-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a9209-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="a9209-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a9209-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a9209-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a9209-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="a9209-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a9209-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a9209-120">E_FAIL</span></span>|<span data-ttu-id="a9209-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="a9209-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a9209-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="a9209-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a9209-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a9209-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a9209-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="a9209-124">E_NOTIMPL</span></span>|<span data-ttu-id="a9209-125">L'host non fornisce un'implementazione di `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="a9209-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9209-126">Note</span><span class="sxs-lookup"><span data-stu-id="a9209-126">Remarks</span></span>  
 <span data-ttu-id="a9209-127">Un host potrebbe richiedere il controllo esclusivo rispetto al numero di thread che possono essere assegnati per elaborare le richieste dei / o, per motivi di implementazione, prestazioni o scalabilità.</span><span class="sxs-lookup"><span data-stu-id="a9209-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="a9209-128">Per questo motivo, l'host non è necessaria per implementare `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="a9209-128">For this reason, the host is not required to implement `SetMinThreads`.</span></span> <span data-ttu-id="a9209-129">In questo caso, l'host deve restituire E_NOTIMPL da questo metodo.</span><span class="sxs-lookup"><span data-stu-id="a9209-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9209-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a9209-130">Requirements</span></span>  
 <span data-ttu-id="a9209-131">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9209-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9209-132">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="a9209-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a9209-133">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a9209-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a9209-134">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9209-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9209-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9209-135">See Also</span></span>  
 [<span data-ttu-id="a9209-136">ICLRIoCompletionManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="a9209-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="a9209-137">SetMaxThreads (metodo)</span><span class="sxs-lookup"><span data-stu-id="a9209-137">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)  
 [<span data-ttu-id="a9209-138">IHostIoCompletionManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="a9209-138">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)

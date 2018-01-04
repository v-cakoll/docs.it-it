---
title: Metodo IHostIoCompletionManager::SetMaxThreads
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.SetMaxThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::SetMaxThreads
helpviewer_keywords:
- IHostIoCompletionManager::SetMaxThreads method [.NET Framework hosting]
- SetMaxThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: ebad4f40-d9f1-4dc6-9b27-a89c9eb3926f
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3d2d8436d85f7be40c89693628794b007e0c6a88
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ihostiocompletionmanagersetmaxthreads-method"></a><span data-ttu-id="fd3b0-102">Metodo IHostIoCompletionManager::SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="fd3b0-102">IHostIoCompletionManager::SetMaxThreads Method</span></span>
<span data-ttu-id="fd3b0-103">Imposta il numero massimo di thread che l'host assegnati per rispondere alle richieste dei / o.</span><span class="sxs-lookup"><span data-stu-id="fd3b0-103">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd3b0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fd3b0-104">Syntax</span></span>  
  
```  
HRESULT SetMaxThreads (  
    [in] DWORD dwMaxIoCompletionThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fd3b0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fd3b0-105">Parameters</span></span>  
 `dwMaxIoCompletionThreads`  
 <span data-ttu-id="fd3b0-106">[in] Il numero massimo di thread da allocare per le richieste dei / o.</span><span class="sxs-lookup"><span data-stu-id="fd3b0-106">[in] The maximum number of threads to allot for I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd3b0-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fd3b0-107">Return Value</span></span>  
  
|<span data-ttu-id="fd3b0-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fd3b0-108">HRESULT</span></span>|<span data-ttu-id="fd3b0-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fd3b0-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fd3b0-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="fd3b0-110">S_OK</span></span>|<span data-ttu-id="fd3b0-111">`SetMaxThreads`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="fd3b0-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="fd3b0-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fd3b0-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fd3b0-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="fd3b0-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fd3b0-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fd3b0-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fd3b0-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="fd3b0-115">The call timed out.</span></span>|  
|<span data-ttu-id="fd3b0-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fd3b0-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fd3b0-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="fd3b0-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fd3b0-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fd3b0-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fd3b0-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="fd3b0-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fd3b0-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fd3b0-120">E_FAIL</span></span>|<span data-ttu-id="fd3b0-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="fd3b0-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fd3b0-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="fd3b0-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fd3b0-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fd3b0-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fd3b0-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="fd3b0-124">E_NOTIMPL</span></span>|<span data-ttu-id="fd3b0-125">L'host non fornisce un'implementazione di `SetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="fd3b0-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd3b0-126">Note</span><span class="sxs-lookup"><span data-stu-id="fd3b0-126">Remarks</span></span>  
 <span data-ttu-id="fd3b0-127">`SetMaxThreads`fornisce Common Language Runtime con la possibilità di impostare il numero massimo di thread che sono disponibili per soddisfare le richieste sulle porte i/o.</span><span class="sxs-lookup"><span data-stu-id="fd3b0-127">`SetMaxThreads` provides the CLR with an opportunity to set the maximum number of threads that are available to service requests on I/O ports.</span></span> <span data-ttu-id="fd3b0-128">Un host potrebbe essere necessario il controllo esclusivo sulla dimensione del pool di thread, per motivi di implementazione, prestazioni o scalabilità.</span><span class="sxs-lookup"><span data-stu-id="fd3b0-128">A host might need exclusive control over the size of the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="fd3b0-129">Per questo motivo, l'host non è necessaria per implementare `SetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="fd3b0-129">For this reason, the host is not required to implement `SetMaxThreads`.</span></span> <span data-ttu-id="fd3b0-130">In questo caso, un host deve restituire E_NOTIMPL da questo metodo.</span><span class="sxs-lookup"><span data-stu-id="fd3b0-130">In this case, a host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd3b0-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fd3b0-131">Requirements</span></span>  
 <span data-ttu-id="fd3b0-132">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd3b0-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd3b0-133">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="fd3b0-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fd3b0-134">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fd3b0-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fd3b0-135">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd3b0-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd3b0-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd3b0-136">See Also</span></span>  
 [<span data-ttu-id="fd3b0-137">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="fd3b0-137">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="fd3b0-138">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="fd3b0-138">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)

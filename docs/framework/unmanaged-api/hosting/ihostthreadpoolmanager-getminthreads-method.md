---
title: Metodo IHostThreadPoolManager::GetMinThreads
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager.GetMinThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager::GetMinThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMinThreads method [.NET Framework hosting]
- GetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: dc07232b-b2e4-4dab-87e2-3c955974ab48
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8ee8adfb93a3e098bb6df69ad00202118bc1731e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a><span data-ttu-id="7c49b-102">Metodo IHostThreadPoolManager::GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="7c49b-102">IHostThreadPoolManager::GetMinThreads Method</span></span>
<span data-ttu-id="7c49b-103">Ottiene il numero minimo di thread inattivi che gestisce l'host nel pool di thread in attesa di richieste.</span><span class="sxs-lookup"><span data-stu-id="7c49b-103">Gets the minimum number of idle threads that the host maintains in the thread pool in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c49b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7c49b-104">Syntax</span></span>  
  
```  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7c49b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7c49b-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="7c49b-106">[out] Puntatore al numero minimo di thread di lavoro inattivi attualmente gestiti dall'host.</span><span class="sxs-lookup"><span data-stu-id="7c49b-106">[out] A pointer to the minimum number of idle worker threads that the host currently maintains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c49b-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7c49b-107">Return Value</span></span>  
  
|<span data-ttu-id="7c49b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7c49b-108">HRESULT</span></span>|<span data-ttu-id="7c49b-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7c49b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7c49b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7c49b-110">S_OK</span></span>|<span data-ttu-id="7c49b-111">`GetMinThreads`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="7c49b-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="7c49b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7c49b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7c49b-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7c49b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7c49b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7c49b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7c49b-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7c49b-115">The call timed out.</span></span>|  
|<span data-ttu-id="7c49b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7c49b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7c49b-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="7c49b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7c49b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7c49b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7c49b-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="7c49b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7c49b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7c49b-120">E_FAIL</span></span>|<span data-ttu-id="7c49b-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="7c49b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7c49b-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="7c49b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7c49b-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7c49b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7c49b-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="7c49b-124">E_NOTIMPL</span></span>|<span data-ttu-id="7c49b-125">L'host non fornisce un'implementazione di `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="7c49b-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c49b-126">Note</span><span class="sxs-lookup"><span data-stu-id="7c49b-126">Remarks</span></span>  
 <span data-ttu-id="7c49b-127">L'host non è necessario fornire un'implementazione di `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="7c49b-127">The host is not required to provide an implementation of `GetMinThreads`.</span></span> <span data-ttu-id="7c49b-128">In questo caso, restituisce un valore HRESULT di E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="7c49b-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c49b-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7c49b-129">Requirements</span></span>  
 <span data-ttu-id="7c49b-130">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c49b-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c49b-131">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="7c49b-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7c49b-132">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7c49b-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c49b-133">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c49b-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c49b-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c49b-134">See Also</span></span>  
 <xref:System.Threading.ThreadPool.GetMinThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="7c49b-135">GetMaxThreads (metodo)</span><span class="sxs-lookup"><span data-stu-id="7c49b-135">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)  
 [<span data-ttu-id="7c49b-136">SetMinThreads (metodo)</span><span class="sxs-lookup"><span data-stu-id="7c49b-136">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)  
 [<span data-ttu-id="7c49b-137">IHostThreadPoolManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="7c49b-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)

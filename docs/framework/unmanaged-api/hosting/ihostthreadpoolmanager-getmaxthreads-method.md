---
title: Metodo IHostThreadPoolManager::GetMaxThreads
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager.GetMaxThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager::GetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: db268876-6178-4a81-aca3-318ee7f96001
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fd15b1448c23785437b3dc62562b5d96abb3601c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostthreadpoolmanagergetmaxthreads-method"></a><span data-ttu-id="fe07a-102">Metodo IHostThreadPoolManager::GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="fe07a-102">IHostThreadPoolManager::GetMaxThreads Method</span></span>
<span data-ttu-id="fe07a-103">Ottiene il numero massimo di thread gestiti dall'host contemporaneamente nel pool di thread.</span><span class="sxs-lookup"><span data-stu-id="fe07a-103">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe07a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fe07a-104">Syntax</span></span>  
  
```  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxWorkerThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fe07a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fe07a-105">Parameters</span></span>  
 `pdwMaxWorkerThreads`  
 <span data-ttu-id="fe07a-106">[out] Puntatore al numero massimo di thread gestiti dall'host nel pool di thread.</span><span class="sxs-lookup"><span data-stu-id="fe07a-106">[out] A pointer to the maximum number of threads that the host maintains in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe07a-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fe07a-107">Return Value</span></span>  
  
|<span data-ttu-id="fe07a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fe07a-108">HRESULT</span></span>|<span data-ttu-id="fe07a-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fe07a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fe07a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="fe07a-110">S_OK</span></span>|<span data-ttu-id="fe07a-111">`GetMaxThreads`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="fe07a-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="fe07a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fe07a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fe07a-113">Common language runtime (CLR (non è stato caricato in un processo o si trova in uno stato in cui è Impossibile eseguire il codice gestito o un processo di chiamata.</span><span class="sxs-lookup"><span data-stu-id="fe07a-113">The common language runtime (CLR( has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fe07a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fe07a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fe07a-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="fe07a-115">The call timed out.</span></span>|  
|<span data-ttu-id="fe07a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fe07a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fe07a-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="fe07a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fe07a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fe07a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fe07a-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="fe07a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fe07a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fe07a-120">E_FAIL</span></span>|<span data-ttu-id="fe07a-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="fe07a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fe07a-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="fe07a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fe07a-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fe07a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fe07a-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="fe07a-124">E_NOTIMPL</span></span>|<span data-ttu-id="fe07a-125">L'host non fornisce un'implementazione di `GetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="fe07a-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe07a-126">Note</span><span class="sxs-lookup"><span data-stu-id="fe07a-126">Remarks</span></span>  
 <span data-ttu-id="fe07a-127">CLR chiama `GetMaxThreads` per determinare il numero totale di thread nel pool di thread.</span><span class="sxs-lookup"><span data-stu-id="fe07a-127">The CLR calls `GetMaxThreads` to determine the total number of threads in the thread pool.</span></span> <span data-ttu-id="fe07a-128">Il [GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) metodo ottiene il numero di thread che non stanno elaborando gli elementi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="fe07a-128">The [GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) method gets the number of threads that are not currently processing work items.</span></span> <span data-ttu-id="fe07a-129">Tutte le richieste oltre il valore restituito di `pdwMaxWorkerThreads` parametro rimangono in coda fino a quando non diventano disponibili thread.</span><span class="sxs-lookup"><span data-stu-id="fe07a-129">All requests above the returned value of the `pdwMaxWorkerThreads` parameter remain queued until threads become available.</span></span>  
  
 <span data-ttu-id="fe07a-130">Se l'host non fornisce un'implementazione di `GetMaxThreads`, deve restituire un valore HRESULT di E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="fe07a-130">If the host does not provide an implementation of `GetMaxThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe07a-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fe07a-131">Requirements</span></span>  
 <span data-ttu-id="fe07a-132">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe07a-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe07a-133">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="fe07a-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fe07a-134">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fe07a-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fe07a-135">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe07a-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe07a-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe07a-136">See Also</span></span>  
 <xref:System.Threading.ThreadPool.GetMaxThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="fe07a-137">GetMinThreads (metodo)</span><span class="sxs-lookup"><span data-stu-id="fe07a-137">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)  
 [<span data-ttu-id="fe07a-138">SetMaxThreads (metodo)</span><span class="sxs-lookup"><span data-stu-id="fe07a-138">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)  
 [<span data-ttu-id="fe07a-139">IHostThreadPoolManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="fe07a-139">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)

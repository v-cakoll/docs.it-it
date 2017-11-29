---
title: Metodo IHostThreadPoolManager::SetMaxThreads
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager.SetMaxThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager::SetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::SetMaxThreads method [.NET Framework hosting]
- SetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: 77cfd347-95c2-4425-b807-4ecc2a8d4578
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 69465029deb1db191c28313fb9a260d3c5ba5289
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostthreadpoolmanagersetmaxthreads-method"></a><span data-ttu-id="7127b-102">Metodo IHostThreadPoolManager::SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="7127b-102">IHostThreadPoolManager::SetMaxThreads Method</span></span>
<span data-ttu-id="7127b-103">Imposta il numero massimo di thread che l'host può mantenere nel pool di thread.</span><span class="sxs-lookup"><span data-stu-id="7127b-103">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7127b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7127b-104">Syntax</span></span>  
  
```  
HRESULT SetMaxThreads (  
    [in] DWORD MaxThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7127b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7127b-105">Parameters</span></span>  
 `MaxThreads`  
 <span data-ttu-id="7127b-106">Numero massimo di thread di lavoro nel pool di thread.</span><span class="sxs-lookup"><span data-stu-id="7127b-106">The maximum number of worker threads in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7127b-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7127b-107">Return Value</span></span>  
  
|<span data-ttu-id="7127b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7127b-108">HRESULT</span></span>|<span data-ttu-id="7127b-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7127b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7127b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7127b-110">S_OK</span></span>|<span data-ttu-id="7127b-111">`SetMaxThreads`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="7127b-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="7127b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7127b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7127b-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7127b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7127b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7127b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7127b-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7127b-115">The call timed out.</span></span>|  
|<span data-ttu-id="7127b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7127b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7127b-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="7127b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7127b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7127b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7127b-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="7127b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7127b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7127b-120">E_FAIL</span></span>|<span data-ttu-id="7127b-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="7127b-121">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="7127b-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="7127b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7127b-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7127b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7127b-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="7127b-124">E_NOTIMPL</span></span>|<span data-ttu-id="7127b-125">L'host non fornisce un'implementazione di `SetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="7127b-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7127b-126">Note</span><span class="sxs-lookup"><span data-stu-id="7127b-126">Remarks</span></span>  
 <span data-ttu-id="7127b-127">Un host non è necessario per consentire di configurare la dimensione del pool di thread CLR.</span><span class="sxs-lookup"><span data-stu-id="7127b-127">A host is not required to allow the CLR to configure the size of the thread pool.</span></span> <span data-ttu-id="7127b-128">Alcuni host potrebbero il controllo esclusivo sul pool di thread, per motivi di implementazione, prestazioni o scalabilità.</span><span class="sxs-lookup"><span data-stu-id="7127b-128">Some hosts might want exclusive control over the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="7127b-129">In questo caso, un host deve restituire un valore HRESULT di E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="7127b-129">In this case, a host should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7127b-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7127b-130">Requirements</span></span>  
 <span data-ttu-id="7127b-131">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7127b-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7127b-132">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="7127b-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7127b-133">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7127b-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7127b-134">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7127b-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7127b-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7127b-135">See Also</span></span>  
 <xref:System.Threading.ThreadPool.SetMaxThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="7127b-136">GetMaxThreads (metodo)</span><span class="sxs-lookup"><span data-stu-id="7127b-136">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)  
 [<span data-ttu-id="7127b-137">SetMinThreads (metodo)</span><span class="sxs-lookup"><span data-stu-id="7127b-137">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)  
 [<span data-ttu-id="7127b-138">IHostThreadPoolManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="7127b-138">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)

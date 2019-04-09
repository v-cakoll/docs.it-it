---
title: Metodo IHostThreadPoolManager::GetMaxThreads
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: db268876-6178-4a81-aca3-318ee7f96001
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4dce4efeb82f44e2c0d19e95551696b16e9f07ba
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157547"
---
# <a name="ihostthreadpoolmanagergetmaxthreads-method"></a><span data-ttu-id="e7287-102">Metodo IHostThreadPoolManager::GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="e7287-102">IHostThreadPoolManager::GetMaxThreads Method</span></span>
<span data-ttu-id="e7287-103">Ottiene il numero massimo di thread che gestisce l'host contemporaneamente nel pool di thread.</span><span class="sxs-lookup"><span data-stu-id="e7287-103">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7287-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e7287-104">Syntax</span></span>  
  
```  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxWorkerThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7287-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e7287-105">Parameters</span></span>  
 `pdwMaxWorkerThreads`  
 <span data-ttu-id="e7287-106">[out] Puntatore al numero massimo di thread che l'host mantiene il pool di thread.</span><span class="sxs-lookup"><span data-stu-id="e7287-106">[out] A pointer to the maximum number of threads that the host maintains in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e7287-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e7287-107">Return Value</span></span>  
  
|<span data-ttu-id="e7287-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e7287-108">HRESULT</span></span>|<span data-ttu-id="e7287-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e7287-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e7287-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e7287-110">S_OK</span></span>|`GetMaxThreads` <span data-ttu-id="e7287-111">stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="e7287-111">returned successfully.</span></span>|  
|<span data-ttu-id="e7287-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e7287-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e7287-113">Common language runtime (CLR (non è stato caricato in un processo, o Common Language Runtime è in uno stato in cui si non è possibile eseguire codice gestito o un processo di chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="e7287-113">The common language runtime (CLR( has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e7287-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e7287-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e7287-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="e7287-115">The call timed out.</span></span>|  
|<span data-ttu-id="e7287-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e7287-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e7287-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="e7287-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e7287-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e7287-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e7287-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="e7287-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e7287-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e7287-120">E_FAIL</span></span>|<span data-ttu-id="e7287-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="e7287-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e7287-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="e7287-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e7287-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e7287-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e7287-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="e7287-124">E_NOTIMPL</span></span>|<span data-ttu-id="e7287-125">L'host non fornisce un'implementazione di `GetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="e7287-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7287-126">Note</span><span class="sxs-lookup"><span data-stu-id="e7287-126">Remarks</span></span>  
 <span data-ttu-id="e7287-127">CLR chiama `GetMaxThreads` per determinare il numero totale di thread nel pool di thread.</span><span class="sxs-lookup"><span data-stu-id="e7287-127">The CLR calls `GetMaxThreads` to determine the total number of threads in the thread pool.</span></span> <span data-ttu-id="e7287-128">Il [GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) metodo ottiene il numero di thread che non stanno elaborando gli elementi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e7287-128">The [GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) method gets the number of threads that are not currently processing work items.</span></span> <span data-ttu-id="e7287-129">Tutte le richieste di oltre il valore restituito di `pdwMaxWorkerThreads` parametro rimangono in coda fino a quando non diventano disponibili thread.</span><span class="sxs-lookup"><span data-stu-id="e7287-129">All requests above the returned value of the `pdwMaxWorkerThreads` parameter remain queued until threads become available.</span></span>  
  
 <span data-ttu-id="e7287-130">Se l'host non fornisce un'implementazione di `GetMaxThreads`, deve restituire un valore HRESULT E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="e7287-130">If the host does not provide an implementation of `GetMaxThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7287-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e7287-131">Requirements</span></span>  
 <span data-ttu-id="e7287-132">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7287-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7287-133">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e7287-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e7287-134">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="e7287-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="e7287-135">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e7287-135">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e7287-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7287-136">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="e7287-137">Metodo GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="e7287-137">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)
- [<span data-ttu-id="e7287-138">Metodo SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="e7287-138">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)
- [<span data-ttu-id="e7287-139">Interfaccia IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="e7287-139">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)

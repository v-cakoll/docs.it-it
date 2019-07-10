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
ms.openlocfilehash: 1d5b865906f797c25783c4d8a306dc91769ef9a9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749286"
---
# <a name="ihostthreadpoolmanagergetmaxthreads-method"></a><span data-ttu-id="a33c0-102">Metodo IHostThreadPoolManager::GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="a33c0-102">IHostThreadPoolManager::GetMaxThreads Method</span></span>
<span data-ttu-id="a33c0-103">Ottiene il numero massimo di thread che gestisce l'host contemporaneamente nel pool di thread.</span><span class="sxs-lookup"><span data-stu-id="a33c0-103">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a33c0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a33c0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxWorkerThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a33c0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a33c0-105">Parameters</span></span>  
 `pdwMaxWorkerThreads`  
 <span data-ttu-id="a33c0-106">[out] Puntatore al numero massimo di thread che l'host mantiene il pool di thread.</span><span class="sxs-lookup"><span data-stu-id="a33c0-106">[out] A pointer to the maximum number of threads that the host maintains in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a33c0-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a33c0-107">Return Value</span></span>  
  
|<span data-ttu-id="a33c0-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a33c0-108">HRESULT</span></span>|<span data-ttu-id="a33c0-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a33c0-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a33c0-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a33c0-110">S_OK</span></span>|<span data-ttu-id="a33c0-111">`GetMaxThreads` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="a33c0-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="a33c0-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a33c0-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a33c0-113">Common language runtime (CLR (non è stato caricato in un processo, o Common Language Runtime è in uno stato in cui si non è possibile eseguire codice gestito o un processo di chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="a33c0-113">The common language runtime (CLR( has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a33c0-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a33c0-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a33c0-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="a33c0-115">The call timed out.</span></span>|  
|<span data-ttu-id="a33c0-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a33c0-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a33c0-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="a33c0-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a33c0-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a33c0-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a33c0-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="a33c0-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a33c0-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a33c0-120">E_FAIL</span></span>|<span data-ttu-id="a33c0-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="a33c0-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a33c0-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="a33c0-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a33c0-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a33c0-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a33c0-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="a33c0-124">E_NOTIMPL</span></span>|<span data-ttu-id="a33c0-125">L'host non fornisce un'implementazione di `GetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="a33c0-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a33c0-126">Note</span><span class="sxs-lookup"><span data-stu-id="a33c0-126">Remarks</span></span>  
 <span data-ttu-id="a33c0-127">CLR chiama `GetMaxThreads` per determinare il numero totale di thread nel pool di thread.</span><span class="sxs-lookup"><span data-stu-id="a33c0-127">The CLR calls `GetMaxThreads` to determine the total number of threads in the thread pool.</span></span> <span data-ttu-id="a33c0-128">Il [GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) metodo ottiene il numero di thread che non stanno elaborando gli elementi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a33c0-128">The [GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) method gets the number of threads that are not currently processing work items.</span></span> <span data-ttu-id="a33c0-129">Tutte le richieste di oltre il valore restituito di `pdwMaxWorkerThreads` parametro rimangono in coda fino a quando non diventano disponibili thread.</span><span class="sxs-lookup"><span data-stu-id="a33c0-129">All requests above the returned value of the `pdwMaxWorkerThreads` parameter remain queued until threads become available.</span></span>  
  
 <span data-ttu-id="a33c0-130">Se l'host non fornisce un'implementazione di `GetMaxThreads`, deve restituire un valore HRESULT E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="a33c0-130">If the host does not provide an implementation of `GetMaxThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a33c0-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a33c0-131">Requirements</span></span>  
 <span data-ttu-id="a33c0-132">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a33c0-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a33c0-133">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a33c0-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a33c0-134">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="a33c0-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a33c0-135">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a33c0-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a33c0-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a33c0-136">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="a33c0-137">Metodo GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="a33c0-137">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)
- [<span data-ttu-id="a33c0-138">Metodo SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="a33c0-138">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)
- [<span data-ttu-id="a33c0-139">Interfaccia IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="a33c0-139">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)

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
ms.openlocfilehash: e53265556de026e84af7ca345a5f82be3c5ff812
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122048"
---
# <a name="ihostthreadpoolmanagergetmaxthreads-method"></a><span data-ttu-id="5bf65-102">Metodo IHostThreadPoolManager::GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="5bf65-102">IHostThreadPoolManager::GetMaxThreads Method</span></span>
<span data-ttu-id="5bf65-103">Ottiene il numero massimo di thread che l'host gestisce simultaneamente nel pool di thread.</span><span class="sxs-lookup"><span data-stu-id="5bf65-103">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bf65-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5bf65-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxWorkerThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5bf65-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5bf65-105">Parameters</span></span>  
 `pdwMaxWorkerThreads`  
 <span data-ttu-id="5bf65-106">out Puntatore al numero massimo di thread gestiti dall'host nel pool di thread.</span><span class="sxs-lookup"><span data-stu-id="5bf65-106">[out] A pointer to the maximum number of threads that the host maintains in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5bf65-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5bf65-107">Return Value</span></span>  
  
|<span data-ttu-id="5bf65-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5bf65-108">HRESULT</span></span>|<span data-ttu-id="5bf65-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5bf65-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5bf65-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5bf65-110">S_OK</span></span>|<span data-ttu-id="5bf65-111">`GetMaxThreads` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="5bf65-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="5bf65-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5bf65-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5bf65-113">Il Common Language Runtime (CLR (non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="5bf65-113">The common language runtime (CLR( has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5bf65-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5bf65-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5bf65-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="5bf65-115">The call timed out.</span></span>|  
|<span data-ttu-id="5bf65-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5bf65-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5bf65-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="5bf65-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5bf65-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5bf65-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5bf65-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="5bf65-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5bf65-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5bf65-120">E_FAIL</span></span>|<span data-ttu-id="5bf65-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="5bf65-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5bf65-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="5bf65-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5bf65-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5bf65-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5bf65-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="5bf65-124">E_NOTIMPL</span></span>|<span data-ttu-id="5bf65-125">L'host non fornisce un'implementazione di `GetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="5bf65-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5bf65-126">Note</span><span class="sxs-lookup"><span data-stu-id="5bf65-126">Remarks</span></span>  
 <span data-ttu-id="5bf65-127">CLR chiama `GetMaxThreads` per determinare il numero totale di thread nel pool di thread.</span><span class="sxs-lookup"><span data-stu-id="5bf65-127">The CLR calls `GetMaxThreads` to determine the total number of threads in the thread pool.</span></span> <span data-ttu-id="5bf65-128">Il metodo [GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) ottiene il numero di thread che attualmente non elaborano elementi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5bf65-128">The [GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) method gets the number of threads that are not currently processing work items.</span></span> <span data-ttu-id="5bf65-129">Tutte le richieste sopra il valore restituito del parametro `pdwMaxWorkerThreads` rimangono in coda fino a quando i thread non diventano disponibili.</span><span class="sxs-lookup"><span data-stu-id="5bf65-129">All requests above the returned value of the `pdwMaxWorkerThreads` parameter remain queued until threads become available.</span></span>  
  
 <span data-ttu-id="5bf65-130">Se l'host non fornisce un'implementazione di `GetMaxThreads`, deve restituire un valore HRESULT di E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="5bf65-130">If the host does not provide an implementation of `GetMaxThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bf65-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5bf65-131">Requirements</span></span>  
 <span data-ttu-id="5bf65-132">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5bf65-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bf65-133">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5bf65-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5bf65-134">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5bf65-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5bf65-135">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bf65-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bf65-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5bf65-136">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="5bf65-137">Metodo GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="5bf65-137">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)
- [<span data-ttu-id="5bf65-138">Metodo SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="5bf65-138">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)
- [<span data-ttu-id="5bf65-139">Interfaccia IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="5bf65-139">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)

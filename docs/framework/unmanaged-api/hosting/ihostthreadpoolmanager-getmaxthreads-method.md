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
ms.openlocfilehash: efbfa310c90f48c99219cb185f090a1b854949a2
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842283"
---
# <a name="ihostthreadpoolmanagergetmaxthreads-method"></a><span data-ttu-id="f6156-102">Metodo IHostThreadPoolManager::GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="f6156-102">IHostThreadPoolManager::GetMaxThreads Method</span></span>
<span data-ttu-id="f6156-103">Ottiene il numero massimo di thread che l'host gestisce simultaneamente nel pool di thread.</span><span class="sxs-lookup"><span data-stu-id="f6156-103">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6156-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f6156-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxWorkerThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6156-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f6156-105">Parameters</span></span>  
 `pdwMaxWorkerThreads`  
 <span data-ttu-id="f6156-106">out Puntatore al numero massimo di thread gestiti dall'host nel pool di thread.</span><span class="sxs-lookup"><span data-stu-id="f6156-106">[out] A pointer to the maximum number of threads that the host maintains in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6156-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f6156-107">Return Value</span></span>  
  
|<span data-ttu-id="f6156-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f6156-108">HRESULT</span></span>|<span data-ttu-id="f6156-109">Description</span><span class="sxs-lookup"><span data-stu-id="f6156-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f6156-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f6156-110">S_OK</span></span>|<span data-ttu-id="f6156-111">`GetMaxThreads`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="f6156-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="f6156-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f6156-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f6156-113">Il Common Language Runtime (CLR (non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="f6156-113">The common language runtime (CLR( has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f6156-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f6156-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f6156-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f6156-115">The call timed out.</span></span>|  
|<span data-ttu-id="f6156-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f6156-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f6156-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="f6156-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f6156-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f6156-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f6156-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="f6156-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f6156-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f6156-120">E_FAIL</span></span>|<span data-ttu-id="f6156-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="f6156-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f6156-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="f6156-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f6156-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f6156-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f6156-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="f6156-124">E_NOTIMPL</span></span>|<span data-ttu-id="f6156-125">L'host non fornisce un'implementazione di `GetMaxThreads` .</span><span class="sxs-lookup"><span data-stu-id="f6156-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6156-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f6156-126">Remarks</span></span>  
 <span data-ttu-id="f6156-127">CLR chiama `GetMaxThreads` per determinare il numero totale di thread nel pool di thread.</span><span class="sxs-lookup"><span data-stu-id="f6156-127">The CLR calls `GetMaxThreads` to determine the total number of threads in the thread pool.</span></span> <span data-ttu-id="f6156-128">Il metodo [GetAvailableThreads](ihostthreadpoolmanager-getavailablethreads-method.md) ottiene il numero di thread che attualmente non elaborano elementi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f6156-128">The [GetAvailableThreads](ihostthreadpoolmanager-getavailablethreads-method.md) method gets the number of threads that are not currently processing work items.</span></span> <span data-ttu-id="f6156-129">Tutte le richieste sopra il valore restituito del `pdwMaxWorkerThreads` parametro rimangono accodate fino a quando i thread diventano disponibili.</span><span class="sxs-lookup"><span data-stu-id="f6156-129">All requests above the returned value of the `pdwMaxWorkerThreads` parameter remain queued until threads become available.</span></span>  
  
 <span data-ttu-id="f6156-130">Se l'host non fornisce un'implementazione di `GetMaxThreads` , deve restituire un valore HRESULT pari a E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="f6156-130">If the host does not provide an implementation of `GetMaxThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6156-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f6156-131">Requirements</span></span>  
 <span data-ttu-id="f6156-132">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6156-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6156-133">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f6156-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f6156-134">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f6156-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f6156-135">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6156-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6156-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6156-136">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="f6156-137">Metodo GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="f6156-137">GetMinThreads Method</span></span>](ihostthreadpoolmanager-getminthreads-method.md)
- [<span data-ttu-id="f6156-138">Metodo SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="f6156-138">SetMaxThreads Method</span></span>](ihostthreadpoolmanager-setmaxthreads-method.md)
- [<span data-ttu-id="f6156-139">Interfaccia IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="f6156-139">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)

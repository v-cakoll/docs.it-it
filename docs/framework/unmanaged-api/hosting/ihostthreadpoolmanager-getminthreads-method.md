---
title: Metodo IHostThreadPoolManager::GetMinThreads
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetMinThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMinThreads method [.NET Framework hosting]
- GetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: dc07232b-b2e4-4dab-87e2-3c955974ab48
topic_type:
- apiref
ms.openlocfilehash: a05cfb43b5b4a328d22c4df04049a7fa156ca080
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2020
ms.locfileid: "83841932"
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a><span data-ttu-id="745ee-102">Metodo IHostThreadPoolManager::GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="745ee-102">IHostThreadPoolManager::GetMinThreads Method</span></span>
<span data-ttu-id="745ee-103">Ottiene il numero minimo di thread inattivi gestiti dall'host nel pool di thread in attesa di richieste.</span><span class="sxs-lookup"><span data-stu-id="745ee-103">Gets the minimum number of idle threads that the host maintains in the thread pool in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="745ee-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="745ee-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="745ee-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="745ee-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="745ee-106">out Puntatore al numero minimo di thread di lavoro inattivi attualmente gestiti dall'host.</span><span class="sxs-lookup"><span data-stu-id="745ee-106">[out] A pointer to the minimum number of idle worker threads that the host currently maintains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="745ee-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="745ee-107">Return Value</span></span>  
  
|<span data-ttu-id="745ee-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="745ee-108">HRESULT</span></span>|<span data-ttu-id="745ee-109">Description</span><span class="sxs-lookup"><span data-stu-id="745ee-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="745ee-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="745ee-110">S_OK</span></span>|<span data-ttu-id="745ee-111">`GetMinThreads`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="745ee-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="745ee-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="745ee-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="745ee-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="745ee-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="745ee-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="745ee-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="745ee-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="745ee-115">The call timed out.</span></span>|  
|<span data-ttu-id="745ee-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="745ee-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="745ee-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="745ee-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="745ee-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="745ee-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="745ee-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="745ee-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="745ee-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="745ee-120">E_FAIL</span></span>|<span data-ttu-id="745ee-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="745ee-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="745ee-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="745ee-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="745ee-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="745ee-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="745ee-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="745ee-124">E_NOTIMPL</span></span>|<span data-ttu-id="745ee-125">L'host non fornisce un'implementazione di `GetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="745ee-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="745ee-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="745ee-126">Remarks</span></span>  
 <span data-ttu-id="745ee-127">L'host non deve fornire un'implementazione di `GetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="745ee-127">The host is not required to provide an implementation of `GetMinThreads`.</span></span> <span data-ttu-id="745ee-128">In questo caso, deve restituire un valore HRESULT pari a E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="745ee-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="745ee-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="745ee-129">Requirements</span></span>  
 <span data-ttu-id="745ee-130">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="745ee-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="745ee-131">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="745ee-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="745ee-132">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="745ee-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="745ee-133">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="745ee-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="745ee-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="745ee-134">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="745ee-135">Metodo GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="745ee-135">GetMaxThreads Method</span></span>](ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="745ee-136">Metodo SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="745ee-136">SetMinThreads Method</span></span>](ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="745ee-137">Interfaccia IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="745ee-137">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)

---
title: Metodo IHostThreadPoolManager::SetMinThreads
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.SetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: 10409db9-9fd2-4e4d-b8cd-cf6fec0afaa2
topic_type:
- apiref
ms.openlocfilehash: c5b150b161acba3820ced367049f08153dd091aa
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842439"
---
# <a name="ihostthreadpoolmanagersetminthreads-method"></a><span data-ttu-id="e74f3-102">Metodo IHostThreadPoolManager::SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="e74f3-102">IHostThreadPoolManager::SetMinThreads Method</span></span>
<span data-ttu-id="e74f3-103">Imposta il numero minimo di thread inattivi che l'host deve gestire in previsione di richieste.</span><span class="sxs-lookup"><span data-stu-id="e74f3-103">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e74f3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e74f3-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMinThreads (  
    [in] DWORD MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e74f3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e74f3-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="e74f3-106">in Nuovo numero minimo di thread che l'host deve gestire.</span><span class="sxs-lookup"><span data-stu-id="e74f3-106">[in] The new minimum number of threads that the host must maintain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e74f3-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e74f3-107">Return Value</span></span>  
  
|<span data-ttu-id="e74f3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e74f3-108">HRESULT</span></span>|<span data-ttu-id="e74f3-109">Description</span><span class="sxs-lookup"><span data-stu-id="e74f3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e74f3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e74f3-110">S_OK</span></span>|<span data-ttu-id="e74f3-111">`SetMinThreads`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="e74f3-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="e74f3-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e74f3-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e74f3-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="e74f3-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e74f3-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e74f3-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e74f3-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="e74f3-115">The call timed out.</span></span>|  
|<span data-ttu-id="e74f3-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e74f3-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e74f3-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="e74f3-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e74f3-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e74f3-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e74f3-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="e74f3-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e74f3-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e74f3-120">E_FAIL</span></span>|<span data-ttu-id="e74f3-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="e74f3-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e74f3-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="e74f3-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e74f3-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e74f3-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e74f3-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="e74f3-124">E_NOTIMPL</span></span>|<span data-ttu-id="e74f3-125">L'host non fornisce un'implementazione di `SetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="e74f3-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e74f3-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e74f3-126">Remarks</span></span>  
 <span data-ttu-id="e74f3-127">Non è necessario un host per fornire un'implementazione di `SetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="e74f3-127">A host is not required to provide an implementation of `SetMinThreads`.</span></span> <span data-ttu-id="e74f3-128">In questo caso, deve restituire un valore HRESULT pari a E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="e74f3-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e74f3-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e74f3-129">Requirements</span></span>  
 <span data-ttu-id="e74f3-130">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e74f3-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e74f3-131">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e74f3-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e74f3-132">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e74f3-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e74f3-133">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e74f3-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e74f3-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e74f3-134">See also</span></span>

- <xref:System.Threading.ThreadPool.SetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="e74f3-135">Metodo GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="e74f3-135">GetMinThreads Method</span></span>](ihostthreadpoolmanager-getminthreads-method.md)
- [<span data-ttu-id="e74f3-136">Metodo SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="e74f3-136">SetMaxThreads Method</span></span>](ihostthreadpoolmanager-setmaxthreads-method.md)
- [<span data-ttu-id="e74f3-137">Interfaccia IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="e74f3-137">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)

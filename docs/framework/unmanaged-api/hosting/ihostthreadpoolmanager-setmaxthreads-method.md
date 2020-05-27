---
title: Metodo IHostThreadPoolManager::SetMaxThreads
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.SetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::SetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::SetMaxThreads method [.NET Framework hosting]
- SetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: 77cfd347-95c2-4425-b807-4ecc2a8d4578
topic_type:
- apiref
ms.openlocfilehash: 53d42afda6668acc6462c419fcefd6bc1435a34c
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842452"
---
# <a name="ihostthreadpoolmanagersetmaxthreads-method"></a><span data-ttu-id="49bda-102">Metodo IHostThreadPoolManager::SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="49bda-102">IHostThreadPoolManager::SetMaxThreads Method</span></span>
<span data-ttu-id="49bda-103">Imposta il numero massimo di thread che l'host è in grado di gestire nel pool di thread.</span><span class="sxs-lookup"><span data-stu-id="49bda-103">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49bda-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="49bda-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMaxThreads (  
    [in] DWORD MaxThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49bda-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="49bda-105">Parameters</span></span>  
 `MaxThreads`  
 <span data-ttu-id="49bda-106">Numero massimo di thread di lavoro nel pool di thread.</span><span class="sxs-lookup"><span data-stu-id="49bda-106">The maximum number of worker threads in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="49bda-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="49bda-107">Return Value</span></span>  
  
|<span data-ttu-id="49bda-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="49bda-108">HRESULT</span></span>|<span data-ttu-id="49bda-109">Description</span><span class="sxs-lookup"><span data-stu-id="49bda-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="49bda-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="49bda-110">S_OK</span></span>|<span data-ttu-id="49bda-111">`SetMaxThreads`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="49bda-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="49bda-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="49bda-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="49bda-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="49bda-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="49bda-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="49bda-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="49bda-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="49bda-115">The call timed out.</span></span>|  
|<span data-ttu-id="49bda-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="49bda-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="49bda-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="49bda-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="49bda-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="49bda-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="49bda-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="49bda-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="49bda-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="49bda-120">E_FAIL</span></span>|<span data-ttu-id="49bda-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="49bda-121">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="49bda-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="49bda-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="49bda-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="49bda-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="49bda-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="49bda-124">E_NOTIMPL</span></span>|<span data-ttu-id="49bda-125">L'host non fornisce un'implementazione di `SetMaxThreads` .</span><span class="sxs-lookup"><span data-stu-id="49bda-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49bda-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="49bda-126">Remarks</span></span>  
 <span data-ttu-id="49bda-127">Per consentire a CLR di configurare le dimensioni del pool di thread, non è necessario un host.</span><span class="sxs-lookup"><span data-stu-id="49bda-127">A host is not required to allow the CLR to configure the size of the thread pool.</span></span> <span data-ttu-id="49bda-128">Alcuni host possono avere un controllo esclusivo sul pool di thread, per motivi quali l'implementazione, le prestazioni o la scalabilità.</span><span class="sxs-lookup"><span data-stu-id="49bda-128">Some hosts might want exclusive control over the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="49bda-129">In questo caso, un host deve restituire un valore HRESULT pari a E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="49bda-129">In this case, a host should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49bda-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="49bda-130">Requirements</span></span>  
 <span data-ttu-id="49bda-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49bda-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49bda-132">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="49bda-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="49bda-133">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="49bda-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="49bda-134">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49bda-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49bda-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49bda-135">See also</span></span>

- <xref:System.Threading.ThreadPool.SetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="49bda-136">Metodo GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="49bda-136">GetMaxThreads Method</span></span>](ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="49bda-137">Metodo SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="49bda-137">SetMinThreads Method</span></span>](ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="49bda-138">Interfaccia IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="49bda-138">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)

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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f4c2ea6deadeb0e9e1869a4ab064f2a948a74f4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749209"
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a><span data-ttu-id="7fac7-102">Metodo IHostThreadPoolManager::GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="7fac7-102">IHostThreadPoolManager::GetMinThreads Method</span></span>
<span data-ttu-id="7fac7-103">Ottiene il numero minimo di thread inattivi che gestisce l'host nel pool di thread in attesa delle richieste.</span><span class="sxs-lookup"><span data-stu-id="7fac7-103">Gets the minimum number of idle threads that the host maintains in the thread pool in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fac7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7fac7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7fac7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7fac7-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="7fac7-106">[out] Puntatore al numero minimo di thread di lavoro inattive che l'host attualmente gestiti.</span><span class="sxs-lookup"><span data-stu-id="7fac7-106">[out] A pointer to the minimum number of idle worker threads that the host currently maintains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7fac7-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7fac7-107">Return Value</span></span>  
  
|<span data-ttu-id="7fac7-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7fac7-108">HRESULT</span></span>|<span data-ttu-id="7fac7-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7fac7-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7fac7-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7fac7-110">S_OK</span></span>|<span data-ttu-id="7fac7-111">`GetMinThreads` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="7fac7-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="7fac7-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7fac7-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7fac7-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7fac7-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7fac7-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7fac7-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7fac7-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7fac7-115">The call timed out.</span></span>|  
|<span data-ttu-id="7fac7-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7fac7-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7fac7-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="7fac7-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7fac7-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7fac7-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7fac7-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="7fac7-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7fac7-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7fac7-120">E_FAIL</span></span>|<span data-ttu-id="7fac7-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="7fac7-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7fac7-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="7fac7-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7fac7-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7fac7-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7fac7-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="7fac7-124">E_NOTIMPL</span></span>|<span data-ttu-id="7fac7-125">L'host non fornisce un'implementazione di `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="7fac7-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7fac7-126">Note</span><span class="sxs-lookup"><span data-stu-id="7fac7-126">Remarks</span></span>  
 <span data-ttu-id="7fac7-127">L'host non è necessario fornire un'implementazione di `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="7fac7-127">The host is not required to provide an implementation of `GetMinThreads`.</span></span> <span data-ttu-id="7fac7-128">In questo caso, deve restituire un valore HRESULT E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="7fac7-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fac7-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7fac7-129">Requirements</span></span>  
 <span data-ttu-id="7fac7-130">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7fac7-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fac7-131">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7fac7-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7fac7-132">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="7fac7-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7fac7-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fac7-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fac7-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7fac7-134">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="7fac7-135">Metodo GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="7fac7-135">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="7fac7-136">Metodo SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="7fac7-136">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="7fac7-137">Interfaccia IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="7fac7-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)

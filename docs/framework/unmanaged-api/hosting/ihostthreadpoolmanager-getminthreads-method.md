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
ms.openlocfilehash: ec323daf7c0d612d84c86c950c0c7235c7f9ebe7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485252"
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a><span data-ttu-id="56156-102">Metodo IHostThreadPoolManager::GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="56156-102">IHostThreadPoolManager::GetMinThreads Method</span></span>
<span data-ttu-id="56156-103">Ottiene il numero minimo di thread inattivi che gestisce l'host nel pool di thread in attesa delle richieste.</span><span class="sxs-lookup"><span data-stu-id="56156-103">Gets the minimum number of idle threads that the host maintains in the thread pool in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56156-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="56156-104">Syntax</span></span>  
  
```  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56156-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="56156-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="56156-106">[out] Puntatore al numero minimo di thread di lavoro inattive che l'host attualmente gestiti.</span><span class="sxs-lookup"><span data-stu-id="56156-106">[out] A pointer to the minimum number of idle worker threads that the host currently maintains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="56156-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="56156-107">Return Value</span></span>  
  
|<span data-ttu-id="56156-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="56156-108">HRESULT</span></span>|<span data-ttu-id="56156-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="56156-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="56156-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="56156-110">S_OK</span></span>|<span data-ttu-id="56156-111">`GetMinThreads` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="56156-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="56156-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="56156-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="56156-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="56156-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="56156-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="56156-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="56156-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="56156-115">The call timed out.</span></span>|  
|<span data-ttu-id="56156-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="56156-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="56156-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="56156-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="56156-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="56156-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="56156-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="56156-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="56156-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="56156-120">E_FAIL</span></span>|<span data-ttu-id="56156-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="56156-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="56156-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="56156-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="56156-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="56156-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="56156-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="56156-124">E_NOTIMPL</span></span>|<span data-ttu-id="56156-125">L'host non fornisce un'implementazione di `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="56156-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56156-126">Note</span><span class="sxs-lookup"><span data-stu-id="56156-126">Remarks</span></span>  
 <span data-ttu-id="56156-127">L'host non è necessario fornire un'implementazione di `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="56156-127">The host is not required to provide an implementation of `GetMinThreads`.</span></span> <span data-ttu-id="56156-128">In questo caso, deve restituire un valore HRESULT E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="56156-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56156-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="56156-129">Requirements</span></span>  
 <span data-ttu-id="56156-130">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56156-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56156-131">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="56156-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="56156-132">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="56156-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="56156-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56156-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56156-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56156-134">See also</span></span>
- <xref:System.Threading.ThreadPool.GetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="56156-135">Metodo GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="56156-135">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="56156-136">Metodo SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="56156-136">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="56156-137">Interfaccia IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="56156-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)

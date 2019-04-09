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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e290f20feacc59944bb1cafded327f4316ab88d9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59174161"
---
# <a name="ihostthreadpoolmanagersetminthreads-method"></a><span data-ttu-id="09177-102">Metodo IHostThreadPoolManager::SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="09177-102">IHostThreadPoolManager::SetMinThreads Method</span></span>
<span data-ttu-id="09177-103">Imposta il numero minimo di thread inattivi che l'host devono essere conservati in previsione delle richieste.</span><span class="sxs-lookup"><span data-stu-id="09177-103">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09177-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="09177-104">Syntax</span></span>  
  
```  
HRESULT SetMinThreads (  
    [in] DWORD MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09177-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="09177-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="09177-106">[in] Il nuovo numero minimo di thread che l'host devono essere conservati.</span><span class="sxs-lookup"><span data-stu-id="09177-106">[in] The new minimum number of threads that the host must maintain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09177-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="09177-107">Return Value</span></span>  
  
|<span data-ttu-id="09177-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="09177-108">HRESULT</span></span>|<span data-ttu-id="09177-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="09177-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="09177-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="09177-110">S_OK</span></span>|`SetMinThreads` <span data-ttu-id="09177-111">stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="09177-111">returned successfully.</span></span>|  
|<span data-ttu-id="09177-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="09177-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="09177-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="09177-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="09177-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="09177-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="09177-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="09177-115">The call timed out.</span></span>|  
|<span data-ttu-id="09177-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="09177-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="09177-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="09177-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="09177-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="09177-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="09177-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="09177-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="09177-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="09177-120">E_FAIL</span></span>|<span data-ttu-id="09177-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="09177-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="09177-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="09177-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="09177-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="09177-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="09177-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="09177-124">E_NOTIMPL</span></span>|<span data-ttu-id="09177-125">L'host non fornisce un'implementazione di `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="09177-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09177-126">Note</span><span class="sxs-lookup"><span data-stu-id="09177-126">Remarks</span></span>  
 <span data-ttu-id="09177-127">Non è necessario fornire un'implementazione di un host `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="09177-127">A host is not required to provide an implementation of `SetMinThreads`.</span></span> <span data-ttu-id="09177-128">In questo caso, deve restituire un valore HRESULT E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="09177-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09177-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="09177-129">Requirements</span></span>  
 <span data-ttu-id="09177-130">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09177-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09177-131">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="09177-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="09177-132">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="09177-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="09177-133">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="09177-133">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="09177-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09177-134">See also</span></span>

- <xref:System.Threading.ThreadPool.SetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="09177-135">Metodo GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="09177-135">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)
- [<span data-ttu-id="09177-136">Metodo SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="09177-136">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)
- [<span data-ttu-id="09177-137">Interfaccia IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="09177-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)

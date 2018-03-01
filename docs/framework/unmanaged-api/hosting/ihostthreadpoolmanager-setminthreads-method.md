---
title: Metodo IHostThreadPoolManager::SetMinThreads
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4fccfeb616b7a1c6d797ad9d91f47e696c4f3599
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ihostthreadpoolmanagersetminthreads-method"></a><span data-ttu-id="fa05f-102">Metodo IHostThreadPoolManager::SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="fa05f-102">IHostThreadPoolManager::SetMinThreads Method</span></span>
<span data-ttu-id="fa05f-103">Imposta il numero minimo di thread inattivi che l'host devono essere conservati in previsione delle richieste.</span><span class="sxs-lookup"><span data-stu-id="fa05f-103">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa05f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fa05f-104">Syntax</span></span>  
  
```  
HRESULT SetMinThreads (  
    [in] DWORD MinThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fa05f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fa05f-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="fa05f-106">[in] Il nuovo numero minimo di thread che deve gestire l'host.</span><span class="sxs-lookup"><span data-stu-id="fa05f-106">[in] The new minimum number of threads that the host must maintain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa05f-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fa05f-107">Return Value</span></span>  
  
|<span data-ttu-id="fa05f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fa05f-108">HRESULT</span></span>|<span data-ttu-id="fa05f-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fa05f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fa05f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="fa05f-110">S_OK</span></span>|<span data-ttu-id="fa05f-111">`SetMinThreads`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="fa05f-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="fa05f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fa05f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fa05f-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="fa05f-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fa05f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fa05f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fa05f-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="fa05f-115">The call timed out.</span></span>|  
|<span data-ttu-id="fa05f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fa05f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fa05f-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="fa05f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fa05f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fa05f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fa05f-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="fa05f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fa05f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fa05f-120">E_FAIL</span></span>|<span data-ttu-id="fa05f-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="fa05f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fa05f-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="fa05f-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fa05f-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fa05f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fa05f-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="fa05f-124">E_NOTIMPL</span></span>|<span data-ttu-id="fa05f-125">L'host non fornisce un'implementazione di `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="fa05f-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa05f-126">Note</span><span class="sxs-lookup"><span data-stu-id="fa05f-126">Remarks</span></span>  
 <span data-ttu-id="fa05f-127">Non è necessario fornire un'implementazione di un host `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="fa05f-127">A host is not required to provide an implementation of `SetMinThreads`.</span></span> <span data-ttu-id="fa05f-128">In questo caso, restituisce un valore HRESULT di E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="fa05f-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa05f-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fa05f-129">Requirements</span></span>  
 <span data-ttu-id="fa05f-130">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa05f-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa05f-131">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="fa05f-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fa05f-132">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fa05f-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa05f-133">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa05f-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa05f-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa05f-134">See Also</span></span>  
 <xref:System.Threading.ThreadPool.SetMinThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="fa05f-135">Metodo GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="fa05f-135">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)  
 [<span data-ttu-id="fa05f-136">Metodo SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="fa05f-136">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)  
 [<span data-ttu-id="fa05f-137">Interfaccia IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="fa05f-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)

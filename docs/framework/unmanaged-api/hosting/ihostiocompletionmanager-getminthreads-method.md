---
title: Metodo IHostIoCompletionManager::GetMinThreads
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.GetMinThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::GetMinThreads
helpviewer_keywords:
- GetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetMinThreads method [.NET Framework hosting]
ms.assetid: d7a7f733-677d-481c-b3d5-444fcc502b8e
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f90a3f416520cc3f635f19d7ae34d5f9f304e9c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ihostiocompletionmanagergetminthreads-method"></a><span data-ttu-id="9077a-102">Metodo IHostIoCompletionManager::GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="9077a-102">IHostIoCompletionManager::GetMinThreads Method</span></span>
<span data-ttu-id="9077a-103">Ottiene il numero minimo di thread forniti dall'host per l'elaborazione delle richieste dei / o.</span><span class="sxs-lookup"><span data-stu-id="9077a-103">Gets the minimum number of threads that the host provides for processing I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9077a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9077a-104">Syntax</span></span>  
  
```  
HRESULT GetMinThreads (  
    [out] DWORD *pdwMinIOCompletionThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9077a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9077a-105">Parameters</span></span>  
 `pdwMinIOCompletionThreads`  
 <span data-ttu-id="9077a-106">[out] Puntatore al numero minimo di thread che l'host fornisce ai / o di elaborare le richieste.</span><span class="sxs-lookup"><span data-stu-id="9077a-106">[out] A pointer to the minimum number of threads that the host provides to process I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9077a-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9077a-107">Return Value</span></span>  
  
|<span data-ttu-id="9077a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9077a-108">HRESULT</span></span>|<span data-ttu-id="9077a-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9077a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9077a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9077a-110">S_OK</span></span>|<span data-ttu-id="9077a-111">`GetMinThreads`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="9077a-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="9077a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9077a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9077a-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9077a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9077a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9077a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9077a-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9077a-115">The call timed out.</span></span>|  
|<span data-ttu-id="9077a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9077a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9077a-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="9077a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9077a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9077a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9077a-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="9077a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9077a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9077a-120">E_FAIL</span></span>|<span data-ttu-id="9077a-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="9077a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9077a-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="9077a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9077a-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9077a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9077a-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="9077a-124">E_NOTIMPL</span></span>|<span data-ttu-id="9077a-125">L'host non fornisce un'implementazione di `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="9077a-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9077a-126">Note</span><span class="sxs-lookup"><span data-stu-id="9077a-126">Remarks</span></span>  
 <span data-ttu-id="9077a-127">Un host potrebbe richiedere il controllo esclusivo rispetto al numero di thread assegnato per soddisfare le richieste dei / o, per motivi di implementazione, prestazioni o scalabilità.</span><span class="sxs-lookup"><span data-stu-id="9077a-127">A host might want exclusive control over the number of threads allotted to service I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="9077a-128">Per questo motivo, l'host non è necessaria per implementare `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="9077a-128">For this reason, the host is not required to implement `GetMinThreads`.</span></span> <span data-ttu-id="9077a-129">In questo caso, l'host deve restituire E_NOTIMPL da questo metodo.</span><span class="sxs-lookup"><span data-stu-id="9077a-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9077a-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9077a-130">Requirements</span></span>  
 <span data-ttu-id="9077a-131">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9077a-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9077a-132">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="9077a-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9077a-133">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9077a-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9077a-134">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9077a-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9077a-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9077a-135">See Also</span></span>  
 [<span data-ttu-id="9077a-136">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="9077a-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="9077a-137">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="9077a-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)

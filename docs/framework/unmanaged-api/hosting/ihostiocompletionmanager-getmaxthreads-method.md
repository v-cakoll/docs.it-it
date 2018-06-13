---
title: Metodo IHostIoCompletionManager::GetMaxThreads
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetMaxThreads
helpviewer_keywords:
- IHostIoCompletionManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: e7a6cadc-2433-4472-a701-58891abcde45
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8544466edcaca1198d7a7ca92a3f9b9a16847193
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442484"
---
# <a name="ihostiocompletionmanagergetmaxthreads-method"></a><span data-ttu-id="cd606-102">Metodo IHostIoCompletionManager::GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="cd606-102">IHostIoCompletionManager::GetMaxThreads Method</span></span>
<span data-ttu-id="cd606-103">Ottiene il numero massimo di thread che l'host è possibile allocare per rispondere alle richieste dei / o.</span><span class="sxs-lookup"><span data-stu-id="cd606-103">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd606-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cd606-104">Syntax</span></span>  
  
```  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxIoCompletionThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cd606-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cd606-105">Parameters</span></span>  
 `pdwMaxIoCompletionThreads`  
 <span data-ttu-id="cd606-106">[out] Puntatore al numero massimo di thread nel pool di thread che l'host è possibile allocare per rispondere alle richieste dei / o.</span><span class="sxs-lookup"><span data-stu-id="cd606-106">[out] A pointer to the maximum number of threads in the thread pool that the host can allot to service I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd606-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="cd606-107">Return Value</span></span>  
  
|<span data-ttu-id="cd606-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cd606-108">HRESULT</span></span>|<span data-ttu-id="cd606-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cd606-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cd606-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="cd606-110">S_OK</span></span>|<span data-ttu-id="cd606-111">`GetMaxThreads` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="cd606-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="cd606-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cd606-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cd606-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="cd606-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cd606-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cd606-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cd606-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="cd606-115">The call timed out.</span></span>|  
|<span data-ttu-id="cd606-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cd606-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cd606-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="cd606-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cd606-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cd606-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cd606-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="cd606-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cd606-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cd606-120">E_FAIL</span></span>|<span data-ttu-id="cd606-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="cd606-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cd606-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="cd606-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cd606-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="cd606-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="cd606-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="cd606-124">E_NOTIMPL</span></span>|<span data-ttu-id="cd606-125">L'host non fornisce un'implementazione di `GetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="cd606-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd606-126">Note</span><span class="sxs-lookup"><span data-stu-id="cd606-126">Remarks</span></span>  
 <span data-ttu-id="cd606-127">Un host potrebbe richiedere il controllo esclusivo rispetto al numero di thread che possono essere assegnati per elaborare le richieste dei / o, per motivi di implementazione, prestazioni o scalabilità.</span><span class="sxs-lookup"><span data-stu-id="cd606-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="cd606-128">Per questo motivo, l'host non è necessaria per implementare `GetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="cd606-128">For this reason, the host is not required to implement `GetMaxThreads`.</span></span> <span data-ttu-id="cd606-129">In questo caso, l'host deve restituire E_NOTIMPL da questo metodo.</span><span class="sxs-lookup"><span data-stu-id="cd606-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd606-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cd606-130">Requirements</span></span>  
 <span data-ttu-id="cd606-131">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd606-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd606-132">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="cd606-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cd606-133">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="cd606-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cd606-134">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd606-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd606-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd606-135">See Also</span></span>  
 [<span data-ttu-id="cd606-136">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="cd606-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="cd606-137">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="cd606-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)

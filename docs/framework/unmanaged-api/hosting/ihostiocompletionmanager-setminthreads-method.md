---
title: Metodo IHostIoCompletionManager::SetMinThreads
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: dea34b81-8d2b-4cc3-8696-0ad4291d8a92
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5fd37546c63ef5e5f25686e105247555dfeb132a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796747"
---
# <a name="ihostiocompletionmanagersetminthreads-method"></a><span data-ttu-id="88a23-102">Metodo IHostIoCompletionManager::SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="88a23-102">IHostIoCompletionManager::SetMinThreads Method</span></span>
<span data-ttu-id="88a23-103">Imposta il numero minimo di thread che l'host deve allocare fino al completamento dei / o.</span><span class="sxs-lookup"><span data-stu-id="88a23-103">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88a23-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="88a23-104">Syntax</span></span>  
  
```  
HRESULT SetMinThreads (  
    [in] DWORD dwMinIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88a23-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="88a23-105">Parameters</span></span>  
 `dwMinIoCompletionThreads`  
 <span data-ttu-id="88a23-106">[in] Il numero minimo di thread di completamento i/o che l'host deve creare.</span><span class="sxs-lookup"><span data-stu-id="88a23-106">[in] The minimum number of I/O completion threads that the host should create.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="88a23-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="88a23-107">Return Value</span></span>  
  
|<span data-ttu-id="88a23-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="88a23-108">HRESULT</span></span>|<span data-ttu-id="88a23-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="88a23-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="88a23-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="88a23-110">S_OK</span></span>|<span data-ttu-id="88a23-111">`SetMinThreads` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="88a23-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="88a23-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="88a23-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="88a23-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="88a23-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="88a23-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="88a23-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="88a23-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="88a23-115">The call timed out.</span></span>|  
|<span data-ttu-id="88a23-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="88a23-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="88a23-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="88a23-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="88a23-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="88a23-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="88a23-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="88a23-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="88a23-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="88a23-120">E_FAIL</span></span>|<span data-ttu-id="88a23-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="88a23-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="88a23-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="88a23-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="88a23-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="88a23-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="88a23-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="88a23-124">E_NOTIMPL</span></span>|<span data-ttu-id="88a23-125">L'host non fornisce un'implementazione di `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="88a23-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88a23-126">Note</span><span class="sxs-lookup"><span data-stu-id="88a23-126">Remarks</span></span>  
 <span data-ttu-id="88a23-127">Un host potrebbe essere necessario il controllo esclusivo rispetto al numero di thread che possono essere assegnati per elaborare le richieste dei / o, per motivi, ad esempio la scalabilità, prestazioni o implementazione.</span><span class="sxs-lookup"><span data-stu-id="88a23-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="88a23-128">Per questo motivo, l'host non è necessaria per implementare `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="88a23-128">For this reason, the host is not required to implement `SetMinThreads`.</span></span> <span data-ttu-id="88a23-129">In questo caso, l'host deve restituire E_NOTIMPL da questo metodo.</span><span class="sxs-lookup"><span data-stu-id="88a23-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88a23-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="88a23-130">Requirements</span></span>  
 <span data-ttu-id="88a23-131">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88a23-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88a23-132">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="88a23-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="88a23-133">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="88a23-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="88a23-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88a23-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88a23-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88a23-135">See also</span></span>

- [<span data-ttu-id="88a23-136">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="88a23-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="88a23-137">Metodo SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="88a23-137">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)
- [<span data-ttu-id="88a23-138">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="88a23-138">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)

---
title: Metodo IHostIoCompletionManager::SetMaxThreads
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetMaxThreads
helpviewer_keywords:
- IHostIoCompletionManager::SetMaxThreads method [.NET Framework hosting]
- SetMaxThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: ebad4f40-d9f1-4dc6-9b27-a89c9eb3926f
topic_type:
- apiref
ms.openlocfilehash: 55727903a7f3c798e7472de6de5249de98af7ae7
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804666"
---
# <a name="ihostiocompletionmanagersetmaxthreads-method"></a><span data-ttu-id="ba0f1-102">Metodo IHostIoCompletionManager::SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="ba0f1-102">IHostIoCompletionManager::SetMaxThreads Method</span></span>
<span data-ttu-id="ba0f1-103">Imposta il numero massimo di thread allocati dall'host alle richieste di I/O del servizio.</span><span class="sxs-lookup"><span data-stu-id="ba0f1-103">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba0f1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ba0f1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMaxThreads (  
    [in] DWORD dwMaxIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba0f1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ba0f1-105">Parameters</span></span>  
 `dwMaxIoCompletionThreads`  
 <span data-ttu-id="ba0f1-106">in Numero massimo di thread da assegnare per le richieste di I/O.</span><span class="sxs-lookup"><span data-stu-id="ba0f1-106">[in] The maximum number of threads to allot for I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba0f1-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ba0f1-107">Return Value</span></span>  
  
|<span data-ttu-id="ba0f1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ba0f1-108">HRESULT</span></span>|<span data-ttu-id="ba0f1-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ba0f1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ba0f1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ba0f1-110">S_OK</span></span>|<span data-ttu-id="ba0f1-111">`SetMaxThreads`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="ba0f1-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="ba0f1-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ba0f1-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ba0f1-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="ba0f1-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ba0f1-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ba0f1-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ba0f1-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="ba0f1-115">The call timed out.</span></span>|  
|<span data-ttu-id="ba0f1-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ba0f1-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ba0f1-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="ba0f1-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ba0f1-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ba0f1-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ba0f1-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="ba0f1-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ba0f1-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ba0f1-120">E_FAIL</span></span>|<span data-ttu-id="ba0f1-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="ba0f1-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ba0f1-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="ba0f1-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ba0f1-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ba0f1-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ba0f1-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="ba0f1-124">E_NOTIMPL</span></span>|<span data-ttu-id="ba0f1-125">L'host non fornisce un'implementazione di `SetMaxThreads` .</span><span class="sxs-lookup"><span data-stu-id="ba0f1-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba0f1-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ba0f1-126">Remarks</span></span>  
 <span data-ttu-id="ba0f1-127">`SetMaxThreads`fornisce a CLR la possibilità di impostare il numero massimo di thread disponibili per le richieste di servizio sulle porte di I/O.</span><span class="sxs-lookup"><span data-stu-id="ba0f1-127">`SetMaxThreads` provides the CLR with an opportunity to set the maximum number of threads that are available to service requests on I/O ports.</span></span> <span data-ttu-id="ba0f1-128">Un host potrebbe avere bisogno di un controllo esclusivo sulle dimensioni del pool di thread, per motivi quali l'implementazione, le prestazioni o la scalabilità.</span><span class="sxs-lookup"><span data-stu-id="ba0f1-128">A host might need exclusive control over the size of the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="ba0f1-129">Per questo motivo, non è necessario che l'host implementi `SetMaxThreads` .</span><span class="sxs-lookup"><span data-stu-id="ba0f1-129">For this reason, the host is not required to implement `SetMaxThreads`.</span></span> <span data-ttu-id="ba0f1-130">In questo caso, un host deve restituire E_NOTIMPL da questo metodo.</span><span class="sxs-lookup"><span data-stu-id="ba0f1-130">In this case, a host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba0f1-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ba0f1-131">Requirements</span></span>  
 <span data-ttu-id="ba0f1-132">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba0f1-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba0f1-133">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ba0f1-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ba0f1-134">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ba0f1-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ba0f1-135">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba0f1-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba0f1-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba0f1-136">See also</span></span>

- [<span data-ttu-id="ba0f1-137">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="ba0f1-137">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="ba0f1-138">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="ba0f1-138">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)

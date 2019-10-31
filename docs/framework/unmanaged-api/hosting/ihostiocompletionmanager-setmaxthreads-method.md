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
ms.openlocfilehash: 7a16c141d9d07af82bd984955e06199e66ce3bbf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133755"
---
# <a name="ihostiocompletionmanagersetmaxthreads-method"></a><span data-ttu-id="ca37a-102">Metodo IHostIoCompletionManager::SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="ca37a-102">IHostIoCompletionManager::SetMaxThreads Method</span></span>
<span data-ttu-id="ca37a-103">Imposta il numero massimo di thread allocati dall'host alle richieste di I/O del servizio.</span><span class="sxs-lookup"><span data-stu-id="ca37a-103">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca37a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ca37a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMaxThreads (  
    [in] DWORD dwMaxIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca37a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ca37a-105">Parameters</span></span>  
 `dwMaxIoCompletionThreads`  
 <span data-ttu-id="ca37a-106">in Numero massimo di thread da assegnare per le richieste di I/O.</span><span class="sxs-lookup"><span data-stu-id="ca37a-106">[in] The maximum number of threads to allot for I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca37a-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ca37a-107">Return Value</span></span>  
  
|<span data-ttu-id="ca37a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ca37a-108">HRESULT</span></span>|<span data-ttu-id="ca37a-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ca37a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ca37a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ca37a-110">S_OK</span></span>|<span data-ttu-id="ca37a-111">`SetMaxThreads` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ca37a-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="ca37a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ca37a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ca37a-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="ca37a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ca37a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ca37a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ca37a-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="ca37a-115">The call timed out.</span></span>|  
|<span data-ttu-id="ca37a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ca37a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ca37a-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="ca37a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ca37a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ca37a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ca37a-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="ca37a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ca37a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ca37a-120">E_FAIL</span></span>|<span data-ttu-id="ca37a-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="ca37a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ca37a-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="ca37a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ca37a-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ca37a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ca37a-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="ca37a-124">E_NOTIMPL</span></span>|<span data-ttu-id="ca37a-125">L'host non fornisce un'implementazione di `SetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="ca37a-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca37a-126">Note</span><span class="sxs-lookup"><span data-stu-id="ca37a-126">Remarks</span></span>  
 <span data-ttu-id="ca37a-127">`SetMaxThreads` fornisce a CLR la possibilità di impostare il numero massimo di thread disponibili per le richieste di servizio sulle porte di I/O.</span><span class="sxs-lookup"><span data-stu-id="ca37a-127">`SetMaxThreads` provides the CLR with an opportunity to set the maximum number of threads that are available to service requests on I/O ports.</span></span> <span data-ttu-id="ca37a-128">Un host potrebbe avere bisogno di un controllo esclusivo sulle dimensioni del pool di thread, per motivi quali l'implementazione, le prestazioni o la scalabilità.</span><span class="sxs-lookup"><span data-stu-id="ca37a-128">A host might need exclusive control over the size of the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="ca37a-129">Per questo motivo, non è necessario che l'host implementi `SetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="ca37a-129">For this reason, the host is not required to implement `SetMaxThreads`.</span></span> <span data-ttu-id="ca37a-130">In questo caso, un host deve restituire E_NOTIMPL da questo metodo.</span><span class="sxs-lookup"><span data-stu-id="ca37a-130">In this case, a host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca37a-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ca37a-131">Requirements</span></span>  
 <span data-ttu-id="ca37a-132">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca37a-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca37a-133">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ca37a-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ca37a-134">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ca37a-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca37a-135">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca37a-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca37a-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca37a-136">See also</span></span>

- [<span data-ttu-id="ca37a-137">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="ca37a-137">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="ca37a-138">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="ca37a-138">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)

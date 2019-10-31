---
title: Metodo IHostIoCompletionManager::GetMinThreads
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetMinThreads
helpviewer_keywords:
- GetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetMinThreads method [.NET Framework hosting]
ms.assetid: d7a7f733-677d-481c-b3d5-444fcc502b8e
topic_type:
- apiref
ms.openlocfilehash: 2506de5f04840f130fab28518f9db7b58eb6e9ff
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133825"
---
# <a name="ihostiocompletionmanagergetminthreads-method"></a><span data-ttu-id="800de-102">Metodo IHostIoCompletionManager::GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="800de-102">IHostIoCompletionManager::GetMinThreads Method</span></span>
<span data-ttu-id="800de-103">Ottiene il numero minimo di thread fornito dall'host per l'elaborazione delle richieste di I/O.</span><span class="sxs-lookup"><span data-stu-id="800de-103">Gets the minimum number of threads that the host provides for processing I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="800de-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="800de-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMinThreads (  
    [out] DWORD *pdwMinIOCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="800de-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="800de-105">Parameters</span></span>  
 `pdwMinIOCompletionThreads`  
 <span data-ttu-id="800de-106">out Puntatore al numero minimo di thread fornito dall'host per elaborare le richieste di I/O.</span><span class="sxs-lookup"><span data-stu-id="800de-106">[out] A pointer to the minimum number of threads that the host provides to process I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="800de-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="800de-107">Return Value</span></span>  
  
|<span data-ttu-id="800de-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="800de-108">HRESULT</span></span>|<span data-ttu-id="800de-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="800de-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="800de-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="800de-110">S_OK</span></span>|<span data-ttu-id="800de-111">`GetMinThreads` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="800de-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="800de-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="800de-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="800de-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="800de-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="800de-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="800de-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="800de-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="800de-115">The call timed out.</span></span>|  
|<span data-ttu-id="800de-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="800de-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="800de-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="800de-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="800de-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="800de-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="800de-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="800de-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="800de-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="800de-120">E_FAIL</span></span>|<span data-ttu-id="800de-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="800de-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="800de-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="800de-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="800de-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="800de-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="800de-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="800de-124">E_NOTIMPL</span></span>|<span data-ttu-id="800de-125">L'host non fornisce un'implementazione di `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="800de-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="800de-126">Note</span><span class="sxs-lookup"><span data-stu-id="800de-126">Remarks</span></span>  
 <span data-ttu-id="800de-127">Un host potrebbe voler controllare in modo esclusivo il numero di thread assegnati alle richieste di I/O del servizio, per motivi quali l'implementazione, le prestazioni o la scalabilità.</span><span class="sxs-lookup"><span data-stu-id="800de-127">A host might want exclusive control over the number of threads allotted to service I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="800de-128">Per questo motivo, non è necessario che l'host implementi `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="800de-128">For this reason, the host is not required to implement `GetMinThreads`.</span></span> <span data-ttu-id="800de-129">In questo caso, l'host deve restituire E_NOTIMPL da questo metodo.</span><span class="sxs-lookup"><span data-stu-id="800de-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="800de-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="800de-130">Requirements</span></span>  
 <span data-ttu-id="800de-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="800de-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="800de-132">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="800de-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="800de-133">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="800de-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="800de-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="800de-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="800de-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="800de-135">See also</span></span>

- [<span data-ttu-id="800de-136">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="800de-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="800de-137">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="800de-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)

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
ms.openlocfilehash: e748a731f2c6934f58a1cd838cc40ce4fd0e4652
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804725"
---
# <a name="ihostiocompletionmanagergetminthreads-method"></a><span data-ttu-id="2db49-102">Metodo IHostIoCompletionManager::GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="2db49-102">IHostIoCompletionManager::GetMinThreads Method</span></span>
<span data-ttu-id="2db49-103">Ottiene il numero minimo di thread fornito dall'host per l'elaborazione delle richieste di I/O.</span><span class="sxs-lookup"><span data-stu-id="2db49-103">Gets the minimum number of threads that the host provides for processing I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2db49-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2db49-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMinThreads (  
    [out] DWORD *pdwMinIOCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2db49-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2db49-105">Parameters</span></span>  
 `pdwMinIOCompletionThreads`  
 <span data-ttu-id="2db49-106">out Puntatore al numero minimo di thread fornito dall'host per elaborare le richieste di I/O.</span><span class="sxs-lookup"><span data-stu-id="2db49-106">[out] A pointer to the minimum number of threads that the host provides to process I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2db49-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2db49-107">Return Value</span></span>  
  
|<span data-ttu-id="2db49-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2db49-108">HRESULT</span></span>|<span data-ttu-id="2db49-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2db49-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2db49-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2db49-110">S_OK</span></span>|<span data-ttu-id="2db49-111">`GetMinThreads`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="2db49-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="2db49-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2db49-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2db49-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="2db49-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2db49-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2db49-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2db49-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="2db49-115">The call timed out.</span></span>|  
|<span data-ttu-id="2db49-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2db49-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2db49-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="2db49-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2db49-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2db49-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2db49-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="2db49-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2db49-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2db49-120">E_FAIL</span></span>|<span data-ttu-id="2db49-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="2db49-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2db49-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="2db49-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2db49-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2db49-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2db49-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="2db49-124">E_NOTIMPL</span></span>|<span data-ttu-id="2db49-125">L'host non fornisce un'implementazione di `GetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="2db49-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2db49-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2db49-126">Remarks</span></span>  
 <span data-ttu-id="2db49-127">Un host potrebbe voler controllare in modo esclusivo il numero di thread assegnati alle richieste di I/O del servizio, per motivi quali l'implementazione, le prestazioni o la scalabilità.</span><span class="sxs-lookup"><span data-stu-id="2db49-127">A host might want exclusive control over the number of threads allotted to service I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="2db49-128">Per questo motivo, non è necessario che l'host implementi `GetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="2db49-128">For this reason, the host is not required to implement `GetMinThreads`.</span></span> <span data-ttu-id="2db49-129">In questo caso, l'host deve restituire E_NOTIMPL da questo metodo.</span><span class="sxs-lookup"><span data-stu-id="2db49-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2db49-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2db49-130">Requirements</span></span>  
 <span data-ttu-id="2db49-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2db49-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2db49-132">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2db49-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2db49-133">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2db49-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2db49-134">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2db49-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2db49-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2db49-135">See also</span></span>

- [<span data-ttu-id="2db49-136">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="2db49-136">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="2db49-137">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="2db49-137">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)

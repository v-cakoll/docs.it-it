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
ms.openlocfilehash: a97a7abf4f561a5aba41d8019f2ba5bd8e879acd
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804731"
---
# <a name="ihostiocompletionmanagergetmaxthreads-method"></a><span data-ttu-id="57a75-102">Metodo IHostIoCompletionManager::GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="57a75-102">IHostIoCompletionManager::GetMaxThreads Method</span></span>
<span data-ttu-id="57a75-103">Ottiene il numero massimo di thread che l'host può allocare alle richieste di I/O del servizio.</span><span class="sxs-lookup"><span data-stu-id="57a75-103">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57a75-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="57a75-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57a75-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="57a75-105">Parameters</span></span>  
 `pdwMaxIoCompletionThreads`  
 <span data-ttu-id="57a75-106">out Puntatore al numero massimo di thread nel pool di thread che l'host può allocare alle richieste di I/O del servizio.</span><span class="sxs-lookup"><span data-stu-id="57a75-106">[out] A pointer to the maximum number of threads in the thread pool that the host can allot to service I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="57a75-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="57a75-107">Return Value</span></span>  
  
|<span data-ttu-id="57a75-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="57a75-108">HRESULT</span></span>|<span data-ttu-id="57a75-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="57a75-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="57a75-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="57a75-110">S_OK</span></span>|<span data-ttu-id="57a75-111">`GetMaxThreads`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="57a75-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="57a75-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="57a75-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="57a75-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="57a75-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="57a75-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="57a75-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="57a75-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="57a75-115">The call timed out.</span></span>|  
|<span data-ttu-id="57a75-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="57a75-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="57a75-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="57a75-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="57a75-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="57a75-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="57a75-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="57a75-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="57a75-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="57a75-120">E_FAIL</span></span>|<span data-ttu-id="57a75-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="57a75-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="57a75-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="57a75-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="57a75-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="57a75-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="57a75-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="57a75-124">E_NOTIMPL</span></span>|<span data-ttu-id="57a75-125">L'host non fornisce un'implementazione di `GetMaxThreads` .</span><span class="sxs-lookup"><span data-stu-id="57a75-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57a75-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="57a75-126">Remarks</span></span>  
 <span data-ttu-id="57a75-127">Un host potrebbe volere un controllo esclusivo sul numero di thread che possono essere assegnati per elaborare le richieste di I/O, per motivi come l'implementazione, le prestazioni o la scalabilità.</span><span class="sxs-lookup"><span data-stu-id="57a75-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="57a75-128">Per questo motivo, non è necessario che l'host implementi `GetMaxThreads` .</span><span class="sxs-lookup"><span data-stu-id="57a75-128">For this reason, the host is not required to implement `GetMaxThreads`.</span></span> <span data-ttu-id="57a75-129">In questo caso, l'host deve restituire E_NOTIMPL da questo metodo.</span><span class="sxs-lookup"><span data-stu-id="57a75-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57a75-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="57a75-130">Requirements</span></span>  
 <span data-ttu-id="57a75-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57a75-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57a75-132">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="57a75-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="57a75-133">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="57a75-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="57a75-134">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57a75-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57a75-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57a75-135">See also</span></span>

- [<span data-ttu-id="57a75-136">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="57a75-136">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="57a75-137">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="57a75-137">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)

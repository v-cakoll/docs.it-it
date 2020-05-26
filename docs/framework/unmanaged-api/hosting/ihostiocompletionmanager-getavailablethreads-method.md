---
title: Metodo IHostIoCompletionManager::GetAvailableThreads
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: bab363d1-b859-47a4-9884-5661c611cce7
topic_type:
- apiref
ms.openlocfilehash: 7ea7395bb1f185ba59940d76def562ab5440e560
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804757"
---
# <a name="ihostiocompletionmanagergetavailablethreads-method"></a><span data-ttu-id="64be4-102">Metodo IHostIoCompletionManager::GetAvailableThreads</span><span class="sxs-lookup"><span data-stu-id="64be4-102">IHostIoCompletionManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="64be4-103">Ottiene il numero di thread di completamento di I/O, del numero totale di thread gestiti dall'host, che non sono attualmente richieste di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="64be4-103">Gets the number of I/O completion threads, of the total number of threads managed by the host, that are not currently servicing requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64be4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="64be4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64be4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="64be4-105">Parameters</span></span>  
 `pdwAvailableIoCompletionThreads`  
 <span data-ttu-id="64be4-106">out Puntatore al numero di thread di completamento di I/O gestiti dall'host attualmente disponibili per le richieste di servizio.</span><span class="sxs-lookup"><span data-stu-id="64be4-106">[out] A pointer to the number of I/O completion threads managed by the host that are currently available to service requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="64be4-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="64be4-107">Return Value</span></span>  
  
|<span data-ttu-id="64be4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="64be4-108">HRESULT</span></span>|<span data-ttu-id="64be4-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64be4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="64be4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="64be4-110">S_OK</span></span>|<span data-ttu-id="64be4-111">`GetAvailableThreads`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="64be4-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="64be4-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="64be4-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="64be4-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="64be4-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="64be4-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="64be4-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="64be4-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="64be4-115">The call timed out.</span></span>|  
|<span data-ttu-id="64be4-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="64be4-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="64be4-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="64be4-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="64be4-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="64be4-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="64be4-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="64be4-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="64be4-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="64be4-120">E_FAIL</span></span>|<span data-ttu-id="64be4-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="64be4-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="64be4-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="64be4-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="64be4-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="64be4-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="64be4-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="64be4-124">E_NOTIMPL</span></span>|<span data-ttu-id="64be4-125">L'host non fornisce un'implementazione di `GetAvailableThreads` .</span><span class="sxs-lookup"><span data-stu-id="64be4-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64be4-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="64be4-126">Remarks</span></span>  
 <span data-ttu-id="64be4-127">Un host potrebbe volere un controllo esclusivo sulle dimensioni del pool di thread di completamento di I/O, per motivi quali l'implementazione, le prestazioni o la scalabilità.</span><span class="sxs-lookup"><span data-stu-id="64be4-127">A host might want exclusive control over the size of the I/O completion thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="64be4-128">Pertanto, non è necessario che l'host implementi `GetAvailableThreads` .</span><span class="sxs-lookup"><span data-stu-id="64be4-128">Therefore, the host is not required to implement `GetAvailableThreads`.</span></span> <span data-ttu-id="64be4-129">In questo caso, l'host deve restituire E_NOTIMPL da questo metodo.</span><span class="sxs-lookup"><span data-stu-id="64be4-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64be4-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="64be4-130">Requirements</span></span>  
 <span data-ttu-id="64be4-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64be4-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64be4-132">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="64be4-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="64be4-133">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="64be4-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="64be4-134">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64be4-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64be4-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64be4-135">See also</span></span>

- [<span data-ttu-id="64be4-136">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="64be4-136">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="64be4-137">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="64be4-137">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)

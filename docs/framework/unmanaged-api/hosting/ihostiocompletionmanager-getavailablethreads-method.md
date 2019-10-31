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
ms.openlocfilehash: 2fa429979faa04518397cf58aaa62d3e45230a76
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133839"
---
# <a name="ihostiocompletionmanagergetavailablethreads-method"></a><span data-ttu-id="b5002-102">Metodo IHostIoCompletionManager::GetAvailableThreads</span><span class="sxs-lookup"><span data-stu-id="b5002-102">IHostIoCompletionManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="b5002-103">Ottiene il numero di thread di completamento di I/O, del numero totale di thread gestiti dall'host, che non sono attualmente richieste di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="b5002-103">Gets the number of I/O completion threads, of the total number of threads managed by the host, that are not currently servicing requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5002-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b5002-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5002-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b5002-105">Parameters</span></span>  
 `pdwAvailableIoCompletionThreads`  
 <span data-ttu-id="b5002-106">out Puntatore al numero di thread di completamento di I/O gestiti dall'host attualmente disponibili per le richieste di servizio.</span><span class="sxs-lookup"><span data-stu-id="b5002-106">[out] A pointer to the number of I/O completion threads managed by the host that are currently available to service requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b5002-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b5002-107">Return Value</span></span>  
  
|<span data-ttu-id="b5002-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b5002-108">HRESULT</span></span>|<span data-ttu-id="b5002-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b5002-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b5002-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b5002-110">S_OK</span></span>|<span data-ttu-id="b5002-111">`GetAvailableThreads` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="b5002-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="b5002-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b5002-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b5002-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="b5002-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b5002-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b5002-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b5002-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b5002-115">The call timed out.</span></span>|  
|<span data-ttu-id="b5002-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b5002-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b5002-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="b5002-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b5002-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b5002-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b5002-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="b5002-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b5002-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b5002-120">E_FAIL</span></span>|<span data-ttu-id="b5002-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="b5002-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b5002-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="b5002-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b5002-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b5002-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b5002-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="b5002-124">E_NOTIMPL</span></span>|<span data-ttu-id="b5002-125">L'host non fornisce un'implementazione di `GetAvailableThreads`.</span><span class="sxs-lookup"><span data-stu-id="b5002-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5002-126">Note</span><span class="sxs-lookup"><span data-stu-id="b5002-126">Remarks</span></span>  
 <span data-ttu-id="b5002-127">Un host potrebbe volere un controllo esclusivo sulle dimensioni del pool di thread di completamento di I/O, per motivi quali l'implementazione, le prestazioni o la scalabilità.</span><span class="sxs-lookup"><span data-stu-id="b5002-127">A host might want exclusive control over the size of the I/O completion thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="b5002-128">Pertanto, non è necessario che l'host implementi `GetAvailableThreads`.</span><span class="sxs-lookup"><span data-stu-id="b5002-128">Therefore, the host is not required to implement `GetAvailableThreads`.</span></span> <span data-ttu-id="b5002-129">In questo caso, l'host deve restituire E_NOTIMPL da questo metodo.</span><span class="sxs-lookup"><span data-stu-id="b5002-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5002-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b5002-130">Requirements</span></span>  
 <span data-ttu-id="b5002-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5002-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5002-132">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b5002-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b5002-133">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b5002-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b5002-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5002-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5002-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5002-135">See also</span></span>

- [<span data-ttu-id="b5002-136">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="b5002-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="b5002-137">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="b5002-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)

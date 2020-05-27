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
ms.openlocfilehash: 29a2fc5652badcc00378192debccba0356f5339e
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804661"
---
# <a name="ihostiocompletionmanagersetminthreads-method"></a><span data-ttu-id="b2b6c-102">Metodo IHostIoCompletionManager::SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="b2b6c-102">IHostIoCompletionManager::SetMinThreads Method</span></span>
<span data-ttu-id="b2b6c-103">Imposta il numero minimo di thread che l'host deve assegnare al completamento I/O.</span><span class="sxs-lookup"><span data-stu-id="b2b6c-103">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2b6c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b2b6c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMinThreads (  
    [in] DWORD dwMinIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2b6c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b2b6c-105">Parameters</span></span>  
 `dwMinIoCompletionThreads`  
 <span data-ttu-id="b2b6c-106">in Numero minimo di thread di completamento di I/O che devono essere creati dall'host.</span><span class="sxs-lookup"><span data-stu-id="b2b6c-106">[in] The minimum number of I/O completion threads that the host should create.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b2b6c-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b2b6c-107">Return Value</span></span>  
  
|<span data-ttu-id="b2b6c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b2b6c-108">HRESULT</span></span>|<span data-ttu-id="b2b6c-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b2b6c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b2b6c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b2b6c-110">S_OK</span></span>|<span data-ttu-id="b2b6c-111">`SetMinThreads`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="b2b6c-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="b2b6c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b2b6c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b2b6c-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="b2b6c-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b2b6c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b2b6c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b2b6c-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b2b6c-115">The call timed out.</span></span>|  
|<span data-ttu-id="b2b6c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b2b6c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b2b6c-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="b2b6c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b2b6c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b2b6c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b2b6c-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="b2b6c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b2b6c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b2b6c-120">E_FAIL</span></span>|<span data-ttu-id="b2b6c-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="b2b6c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b2b6c-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="b2b6c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b2b6c-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b2b6c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b2b6c-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="b2b6c-124">E_NOTIMPL</span></span>|<span data-ttu-id="b2b6c-125">L'host non fornisce un'implementazione di `SetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="b2b6c-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2b6c-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b2b6c-126">Remarks</span></span>  
 <span data-ttu-id="b2b6c-127">Un host potrebbe volere un controllo esclusivo sul numero di thread che possono essere assegnati per elaborare le richieste di I/O, per motivi come l'implementazione, le prestazioni o la scalabilità.</span><span class="sxs-lookup"><span data-stu-id="b2b6c-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="b2b6c-128">Per questo motivo, non è necessario che l'host implementi `SetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="b2b6c-128">For this reason, the host is not required to implement `SetMinThreads`.</span></span> <span data-ttu-id="b2b6c-129">In questo caso, l'host deve restituire E_NOTIMPL da questo metodo.</span><span class="sxs-lookup"><span data-stu-id="b2b6c-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2b6c-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b2b6c-130">Requirements</span></span>  
 <span data-ttu-id="b2b6c-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2b6c-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2b6c-132">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b2b6c-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b2b6c-133">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b2b6c-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b2b6c-134">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2b6c-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2b6c-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2b6c-135">See also</span></span>

- [<span data-ttu-id="b2b6c-136">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="b2b6c-136">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="b2b6c-137">Metodo SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="b2b6c-137">SetMaxThreads Method</span></span>](ihostiocompletionmanager-setmaxthreads-method.md)
- [<span data-ttu-id="b2b6c-138">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="b2b6c-138">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)

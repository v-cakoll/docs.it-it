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
ms.openlocfilehash: 8b1fc936b601d327ce6306f22dbec2c1078718da
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133739"
---
# <a name="ihostiocompletionmanagersetminthreads-method"></a><span data-ttu-id="c238a-102">Metodo IHostIoCompletionManager::SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="c238a-102">IHostIoCompletionManager::SetMinThreads Method</span></span>
<span data-ttu-id="c238a-103">Imposta il numero minimo di thread che l'host deve assegnare al completamento I/O.</span><span class="sxs-lookup"><span data-stu-id="c238a-103">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c238a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c238a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMinThreads (  
    [in] DWORD dwMinIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c238a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c238a-105">Parameters</span></span>  
 `dwMinIoCompletionThreads`  
 <span data-ttu-id="c238a-106">in Numero minimo di thread di completamento di I/O che devono essere creati dall'host.</span><span class="sxs-lookup"><span data-stu-id="c238a-106">[in] The minimum number of I/O completion threads that the host should create.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c238a-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c238a-107">Return Value</span></span>  
  
|<span data-ttu-id="c238a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c238a-108">HRESULT</span></span>|<span data-ttu-id="c238a-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c238a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c238a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c238a-110">S_OK</span></span>|<span data-ttu-id="c238a-111">`SetMinThreads` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="c238a-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="c238a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c238a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c238a-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="c238a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c238a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c238a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c238a-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="c238a-115">The call timed out.</span></span>|  
|<span data-ttu-id="c238a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c238a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c238a-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="c238a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c238a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c238a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c238a-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="c238a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c238a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c238a-120">E_FAIL</span></span>|<span data-ttu-id="c238a-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="c238a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c238a-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="c238a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c238a-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c238a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c238a-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="c238a-124">E_NOTIMPL</span></span>|<span data-ttu-id="c238a-125">L'host non fornisce un'implementazione di `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="c238a-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c238a-126">Note</span><span class="sxs-lookup"><span data-stu-id="c238a-126">Remarks</span></span>  
 <span data-ttu-id="c238a-127">Un host potrebbe volere un controllo esclusivo sul numero di thread che possono essere assegnati per elaborare le richieste di I/O, per motivi come l'implementazione, le prestazioni o la scalabilità.</span><span class="sxs-lookup"><span data-stu-id="c238a-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="c238a-128">Per questo motivo, non è necessario che l'host implementi `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="c238a-128">For this reason, the host is not required to implement `SetMinThreads`.</span></span> <span data-ttu-id="c238a-129">In questo caso, l'host deve restituire E_NOTIMPL da questo metodo.</span><span class="sxs-lookup"><span data-stu-id="c238a-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c238a-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c238a-130">Requirements</span></span>  
 <span data-ttu-id="c238a-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c238a-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c238a-132">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c238a-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c238a-133">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c238a-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c238a-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c238a-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c238a-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c238a-135">See also</span></span>

- [<span data-ttu-id="c238a-136">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="c238a-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="c238a-137">Metodo SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="c238a-137">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)
- [<span data-ttu-id="c238a-138">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="c238a-138">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)

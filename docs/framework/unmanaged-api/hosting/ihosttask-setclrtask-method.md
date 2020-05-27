---
title: Metodo IHostTask::SetCLRTask
ms.date: 03/30/2017
api_name:
- IHostTask.SetCLRTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::SetCLRTask
helpviewer_keywords:
- SetCLRTask method [.NET Framework hosting]
- IHostTask::SetCLRTask method [.NET Framework hosting]
ms.assetid: e9d39c80-41a1-49e7-bb5e-ea3433bfb5d7
topic_type:
- apiref
ms.openlocfilehash: b6eac134a4ffb1813cdc6957632ce5fb9b1a5fff
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842270"
---
# <a name="ihosttasksetclrtask-method"></a><span data-ttu-id="1562f-102">Metodo IHostTask::SetCLRTask</span><span class="sxs-lookup"><span data-stu-id="1562f-102">IHostTask::SetCLRTask Method</span></span>
<span data-ttu-id="1562f-103">Associa un' `ICLRTask` istanza di all'istanza di [IHostTask](ihosttask-interface.md) corrente.</span><span class="sxs-lookup"><span data-stu-id="1562f-103">Associates an `ICLRTask` instance with the current [IHostTask](ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1562f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1562f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTask (  
    [in] ICLRTask *pCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1562f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1562f-105">Parameters</span></span>  
 `pCLRTask`  
 <span data-ttu-id="1562f-106">in Puntatore di interfaccia all' `ICLRTask` istanza di da associare all' `IHostTask` istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="1562f-106">[in] An interface pointer to the `ICLRTask` instance to be associated with the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1562f-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1562f-107">Return Value</span></span>  
  
|<span data-ttu-id="1562f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1562f-108">HRESULT</span></span>|<span data-ttu-id="1562f-109">Description</span><span class="sxs-lookup"><span data-stu-id="1562f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1562f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1562f-110">S_OK</span></span>|<span data-ttu-id="1562f-111">`SetCLRTask`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="1562f-111">`SetCLRTask` returned successfully.</span></span>|  
|<span data-ttu-id="1562f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1562f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1562f-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="1562f-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1562f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1562f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1562f-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="1562f-115">The call timed out.</span></span>|  
|<span data-ttu-id="1562f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1562f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1562f-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="1562f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1562f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1562f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1562f-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="1562f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1562f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1562f-120">E_FAIL</span></span>|<span data-ttu-id="1562f-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="1562f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1562f-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="1562f-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1562f-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1562f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1562f-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="1562f-124">Remarks</span></span>  
 <span data-ttu-id="1562f-125">CLR chiama `SetCLRTask` per associare un' `ICLRTask` istanza all'istanza corrente `IHostTask` , creata da una chiamata a [IHostTaskManager:: CreateTask](ihosttaskmanager-createtask-method.md).</span><span class="sxs-lookup"><span data-stu-id="1562f-125">The CLR calls `SetCLRTask` to associate an `ICLRTask` instance with the current `IHostTask` instance, which was created by a call to [IHostTaskManager::CreateTask](ihosttaskmanager-createtask-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1562f-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1562f-126">Requirements</span></span>  
 <span data-ttu-id="1562f-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1562f-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1562f-128">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1562f-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1562f-129">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1562f-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1562f-130">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1562f-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1562f-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1562f-131">See also</span></span>

- [<span data-ttu-id="1562f-132">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="1562f-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="1562f-133">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="1562f-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="1562f-134">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="1562f-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="1562f-135">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="1562f-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)

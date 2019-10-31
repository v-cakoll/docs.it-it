---
title: Metodo ICLRTask::YieldTask
ms.date: 03/30/2017
api_name:
- ICLRTask.YieldTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::YieldTask
helpviewer_keywords:
- ICLRTask::YieldTask method [.NET Framework hosting]
- YieldTask method [.NET Framework hosting]
ms.assetid: b8eb4095-3a8f-4be3-9446-63e9893dce7d
topic_type:
- apiref
ms.openlocfilehash: 43f2048c8ab85fa7e94f73aad430400ad4c8352f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124588"
---
# <a name="iclrtaskyieldtask-method"></a><span data-ttu-id="83df3-102">Metodo ICLRTask::YieldTask</span><span class="sxs-lookup"><span data-stu-id="83df3-102">ICLRTask::YieldTask Method</span></span>
<span data-ttu-id="83df3-103">Richiede che il Common Language Runtime (CLR) abbia accantonato l'attività rappresentata dall'istanza corrente di [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) e renda disponibile il tempo del processore ad altre attività.</span><span class="sxs-lookup"><span data-stu-id="83df3-103">Requests that the common language runtime (CLR) put aside the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents, and make the processor time available to other tasks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83df3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="83df3-104">Syntax</span></span>  
  
```cpp  
HRESULT YieldTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="83df3-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="83df3-105">Return Value</span></span>  
  
|<span data-ttu-id="83df3-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="83df3-106">HRESULT</span></span>|<span data-ttu-id="83df3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="83df3-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="83df3-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="83df3-108">S_OK</span></span>|<span data-ttu-id="83df3-109">`YieldTask` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="83df3-109">`YieldTask` returned successfully.</span></span>|  
|<span data-ttu-id="83df3-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="83df3-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="83df3-111">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="83df3-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="83df3-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="83df3-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="83df3-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="83df3-113">The call timed out.</span></span>|  
|<span data-ttu-id="83df3-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="83df3-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="83df3-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="83df3-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="83df3-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="83df3-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="83df3-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="83df3-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="83df3-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="83df3-118">E_FAIL</span></span>|<span data-ttu-id="83df3-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="83df3-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="83df3-120">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="83df3-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="83df3-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="83df3-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83df3-122">Note</span><span class="sxs-lookup"><span data-stu-id="83df3-122">Remarks</span></span>  
 <span data-ttu-id="83df3-123">Un host chiama `YieldTask` per richiedere risorse del processore per altre attività o processi.</span><span class="sxs-lookup"><span data-stu-id="83df3-123">A host calls `YieldTask` to request processor resources for other tasks or processes.</span></span> <span data-ttu-id="83df3-124">Questo metodo è destinato principalmente a consentire al codice con esecuzione prolungata di cedere tempo CPU.</span><span class="sxs-lookup"><span data-stu-id="83df3-124">This method is primarily intended to allow long-running code to give up CPU time.</span></span> <span data-ttu-id="83df3-125">Il runtime tenta di inserire l'attività che l'istanza corrente di `ICLRTask` rappresenta in uno stato in cui può produrre tempo di elaborazione, ma non garantisce la riuscita.</span><span class="sxs-lookup"><span data-stu-id="83df3-125">The runtime attempts to put the task that the current `ICLRTask` instance represents in a state where it can yield processing time, but makes no guarantee of success.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83df3-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="83df3-126">Requirements</span></span>  
 <span data-ttu-id="83df3-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83df3-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83df3-128">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="83df3-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="83df3-129">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="83df3-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="83df3-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83df3-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83df3-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83df3-131">See also</span></span>

- [<span data-ttu-id="83df3-132">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="83df3-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="83df3-133">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="83df3-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="83df3-134">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="83df3-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="83df3-135">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="83df3-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

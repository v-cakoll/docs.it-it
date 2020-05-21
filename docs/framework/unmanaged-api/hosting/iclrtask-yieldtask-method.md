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
ms.openlocfilehash: ccfca2f685a88f5802dd58667fbf1fac14727c88
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762903"
---
# <a name="iclrtaskyieldtask-method"></a><span data-ttu-id="81c60-102">Metodo ICLRTask::YieldTask</span><span class="sxs-lookup"><span data-stu-id="81c60-102">ICLRTask::YieldTask Method</span></span>
<span data-ttu-id="81c60-103">Richiede che il Common Language Runtime (CLR) abbia accantonato l'attività rappresentata dall'istanza corrente di [ICLRTask](iclrtask-interface.md) e renda disponibile il tempo del processore ad altre attività.</span><span class="sxs-lookup"><span data-stu-id="81c60-103">Requests that the common language runtime (CLR) put aside the task that the current [ICLRTask](iclrtask-interface.md) instance represents, and make the processor time available to other tasks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81c60-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="81c60-104">Syntax</span></span>  
  
```cpp  
HRESULT YieldTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="81c60-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="81c60-105">Return Value</span></span>  
  
|<span data-ttu-id="81c60-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="81c60-106">HRESULT</span></span>|<span data-ttu-id="81c60-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="81c60-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="81c60-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="81c60-108">S_OK</span></span>|<span data-ttu-id="81c60-109">`YieldTask`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="81c60-109">`YieldTask` returned successfully.</span></span>|  
|<span data-ttu-id="81c60-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="81c60-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="81c60-111">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="81c60-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="81c60-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="81c60-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="81c60-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="81c60-113">The call timed out.</span></span>|  
|<span data-ttu-id="81c60-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="81c60-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="81c60-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="81c60-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="81c60-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="81c60-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="81c60-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="81c60-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="81c60-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="81c60-118">E_FAIL</span></span>|<span data-ttu-id="81c60-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="81c60-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="81c60-120">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="81c60-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="81c60-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="81c60-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81c60-122">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="81c60-122">Remarks</span></span>  
 <span data-ttu-id="81c60-123">Un host chiama `YieldTask` per richiedere risorse del processore per altre attività o processi.</span><span class="sxs-lookup"><span data-stu-id="81c60-123">A host calls `YieldTask` to request processor resources for other tasks or processes.</span></span> <span data-ttu-id="81c60-124">Questo metodo è destinato principalmente a consentire al codice con esecuzione prolungata di cedere tempo CPU.</span><span class="sxs-lookup"><span data-stu-id="81c60-124">This method is primarily intended to allow long-running code to give up CPU time.</span></span> <span data-ttu-id="81c60-125">Il runtime tenta di inserire l'attività che l' `ICLRTask` istanza corrente rappresenta in uno stato in cui può produrre tempo di elaborazione, ma non garantisce la riuscita.</span><span class="sxs-lookup"><span data-stu-id="81c60-125">The runtime attempts to put the task that the current `ICLRTask` instance represents in a state where it can yield processing time, but makes no guarantee of success.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81c60-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="81c60-126">Requirements</span></span>  
 <span data-ttu-id="81c60-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81c60-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81c60-128">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="81c60-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="81c60-129">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="81c60-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="81c60-130">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81c60-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81c60-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81c60-131">See also</span></span>

- [<span data-ttu-id="81c60-132">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="81c60-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="81c60-133">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="81c60-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="81c60-134">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="81c60-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="81c60-135">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="81c60-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)

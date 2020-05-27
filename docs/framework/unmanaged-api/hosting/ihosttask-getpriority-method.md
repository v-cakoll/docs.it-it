---
title: Metodo IHostTask::GetPriority
ms.date: 03/30/2017
api_name:
- IHostTask.GetPriority
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::GetPriority
helpviewer_keywords:
- GetPriority method [.NET Framework hosting]
- IHostTask::GetPriority method [.NET Framework hosting]
ms.assetid: 4b463cd6-77c1-4f9a-8518-346ad8fc4b70
topic_type:
- apiref
ms.openlocfilehash: e41fcf2f03b024c1b4ae0032c0ff025d6e2aa1c3
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842504"
---
# <a name="ihosttaskgetpriority-method"></a><span data-ttu-id="9a04f-102">Metodo IHostTask::GetPriority</span><span class="sxs-lookup"><span data-stu-id="9a04f-102">IHostTask::GetPriority Method</span></span>
<span data-ttu-id="9a04f-103">Ottiene il livello di priorità del thread dell'attività rappresentata dall'istanza di [IHostTask](ihosttask-interface.md) corrente.</span><span class="sxs-lookup"><span data-stu-id="9a04f-103">Gets the thread priority level of the task represented by the current [IHostTask](ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a04f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a04f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPriority (  
    [out] int *pPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a04f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9a04f-105">Parameters</span></span>  
 `pPriority`  
 <span data-ttu-id="9a04f-106">out Puntatore a un intero che indica il livello di priorità del thread dell'attività rappresentata dall' `IHostTask` istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="9a04f-106">[out] A pointer to an integer that indicates the thread priority level of the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a04f-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9a04f-107">Return Value</span></span>  
  
|<span data-ttu-id="9a04f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9a04f-108">HRESULT</span></span>|<span data-ttu-id="9a04f-109">Description</span><span class="sxs-lookup"><span data-stu-id="9a04f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9a04f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9a04f-110">S_OK</span></span>|<span data-ttu-id="9a04f-111">`GetPriority`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="9a04f-111">`GetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="9a04f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9a04f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9a04f-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="9a04f-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9a04f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9a04f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9a04f-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9a04f-115">The call timed out.</span></span>|  
|<span data-ttu-id="9a04f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9a04f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9a04f-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="9a04f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9a04f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9a04f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9a04f-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="9a04f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9a04f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9a04f-120">E_FAIL</span></span>|<span data-ttu-id="9a04f-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="9a04f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9a04f-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="9a04f-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9a04f-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9a04f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a04f-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9a04f-124">Remarks</span></span>  
 <span data-ttu-id="9a04f-125">I valori del livello di priorità dei thread sono definiti dalla `SetThreadPriority` funzione Win32.</span><span class="sxs-lookup"><span data-stu-id="9a04f-125">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a04f-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9a04f-126">Requirements</span></span>  
 <span data-ttu-id="9a04f-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a04f-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a04f-128">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9a04f-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9a04f-129">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9a04f-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9a04f-130">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a04f-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a04f-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a04f-131">See also</span></span>

- [<span data-ttu-id="9a04f-132">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="9a04f-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="9a04f-133">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="9a04f-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="9a04f-134">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="9a04f-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="9a04f-135">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="9a04f-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)

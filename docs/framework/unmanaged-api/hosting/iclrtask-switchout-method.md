---
title: Metodo ICLRTask::SwitchOut
ms.date: 03/30/2017
api_name:
- ICLRTask.SwitchOut
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchOut
helpviewer_keywords:
- ICLRTask::SwitchOut method [.NET Framework hosting]
- SwitchOut method [.NET Framework hosting]
ms.assetid: b6fb168c-b24b-4ecf-a390-2b5ba3317ae6
topic_type:
- apiref
ms.openlocfilehash: 75517ae55ebae07242f19c19c5473780ce4b0809
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762916"
---
# <a name="iclrtaskswitchout-method"></a><span data-ttu-id="a59ba-102">Metodo ICLRTask::SwitchOut</span><span class="sxs-lookup"><span data-stu-id="a59ba-102">ICLRTask::SwitchOut Method</span></span>
<span data-ttu-id="a59ba-103">Notifica al Common Language Runtime (CLR) che l'attività rappresentata dall'istanza corrente di [ICLRTask](iclrtask-interface.md) non è più in uno stato eseguibile.</span><span class="sxs-lookup"><span data-stu-id="a59ba-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](iclrtask-interface.md) instance is no longer in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a59ba-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a59ba-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchOut ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a59ba-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a59ba-105">Return Value</span></span>  
  
|<span data-ttu-id="a59ba-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a59ba-106">HRESULT</span></span>|<span data-ttu-id="a59ba-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a59ba-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a59ba-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="a59ba-108">S_OK</span></span>|<span data-ttu-id="a59ba-109">`SwitchOut`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="a59ba-109">`SwitchOut` returned successfully.</span></span>|  
|<span data-ttu-id="a59ba-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a59ba-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a59ba-111">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="a59ba-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a59ba-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a59ba-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a59ba-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="a59ba-113">The call timed out.</span></span>|  
|<span data-ttu-id="a59ba-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a59ba-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a59ba-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="a59ba-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a59ba-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a59ba-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a59ba-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="a59ba-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a59ba-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a59ba-118">E_FAIL</span></span>|<span data-ttu-id="a59ba-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="a59ba-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a59ba-120">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="a59ba-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a59ba-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a59ba-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a59ba-122">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a59ba-122">Remarks</span></span>  
 <span data-ttu-id="a59ba-123">Un host chiama `SwitchOut` per informare il CLR che ha interrotto temporaneamente l'esecuzione dell'attività `ICLRTask` rappresentata dall'istanza corrente e Ripianifica l'attività.</span><span class="sxs-lookup"><span data-stu-id="a59ba-123">A host calls `SwitchOut` to inform the CLR that it has temporarily stopped executing the task that the current `ICLRTask` instance represents, and will reschedule the task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a59ba-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a59ba-124">Requirements</span></span>  
 <span data-ttu-id="a59ba-125">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a59ba-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a59ba-126">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a59ba-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a59ba-127">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a59ba-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a59ba-128">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a59ba-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a59ba-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a59ba-129">See also</span></span>

- [<span data-ttu-id="a59ba-130">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="a59ba-130">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="a59ba-131">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="a59ba-131">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="a59ba-132">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="a59ba-132">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="a59ba-133">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="a59ba-133">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)

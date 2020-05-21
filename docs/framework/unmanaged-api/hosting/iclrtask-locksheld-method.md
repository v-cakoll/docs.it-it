---
title: Metodo ICLRTask::LocksHeld
ms.date: 03/30/2017
api_name:
- ICLRTask.LocksHeld
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::LocksHeld
helpviewer_keywords:
- LocksHeld method [.NET Framework hosting]
- ICLRTask::LocksHeld method [.NET Framework hosting]
ms.assetid: e88a4dc3-02cc-4703-a474-292b71c40657
topic_type:
- apiref
ms.openlocfilehash: c67f00acd61d6e0cdf3adfa0d3d0fda2a06a6f31
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762983"
---
# <a name="iclrtasklocksheld-method"></a><span data-ttu-id="ed833-102">Metodo ICLRTask::LocksHeld</span><span class="sxs-lookup"><span data-stu-id="ed833-102">ICLRTask::LocksHeld Method</span></span>
<span data-ttu-id="ed833-103">Ottiene il numero di blocchi attualmente conservati nell'attività.</span><span class="sxs-lookup"><span data-stu-id="ed833-103">Gets the number of locks currently held on the task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed833-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ed833-104">Syntax</span></span>  
  
```cpp  
HRESULT LocksHeld (  
    [out] SIZE_T *pLockCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed833-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ed833-105">Parameters</span></span>  
 `pLockCount`  
 <span data-ttu-id="ed833-106">out Numero di blocchi conservati nell'attività al momento della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="ed833-106">[out] The number of locks held on the task at the time of the method call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ed833-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ed833-107">Return Value</span></span>  
  
|<span data-ttu-id="ed833-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ed833-108">HRESULT</span></span>|<span data-ttu-id="ed833-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ed833-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ed833-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ed833-110">S_OK</span></span>|<span data-ttu-id="ed833-111">`LocksHeld`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="ed833-111">`LocksHeld` returned successfully.</span></span>|  
|<span data-ttu-id="ed833-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ed833-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ed833-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="ed833-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ed833-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ed833-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ed833-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="ed833-115">The call timed out.</span></span>|  
|<span data-ttu-id="ed833-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ed833-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ed833-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="ed833-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ed833-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ed833-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ed833-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="ed833-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ed833-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ed833-120">E_FAIL</span></span>|<span data-ttu-id="ed833-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="ed833-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ed833-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="ed833-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ed833-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ed833-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ed833-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ed833-124">Requirements</span></span>  
 <span data-ttu-id="ed833-125">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed833-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed833-126">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ed833-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ed833-127">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ed833-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ed833-128">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed833-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed833-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed833-129">See also</span></span>

- [<span data-ttu-id="ed833-130">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="ed833-130">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="ed833-131">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="ed833-131">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="ed833-132">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="ed833-132">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="ed833-133">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="ed833-133">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)

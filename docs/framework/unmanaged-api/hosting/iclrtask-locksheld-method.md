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
ms.openlocfilehash: 3a3c42e2877957e3bbf5031e6ba650e4c9e0364e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195940"
---
# <a name="iclrtasklocksheld-method"></a><span data-ttu-id="9de65-102">Metodo ICLRTask::LocksHeld</span><span class="sxs-lookup"><span data-stu-id="9de65-102">ICLRTask::LocksHeld Method</span></span>
<span data-ttu-id="9de65-103">Ottiene il numero di blocchi attualmente conservati nell'attività.</span><span class="sxs-lookup"><span data-stu-id="9de65-103">Gets the number of locks currently held on the task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9de65-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9de65-104">Syntax</span></span>  
  
```cpp  
HRESULT LocksHeld (  
    [out] SIZE_T *pLockCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9de65-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9de65-105">Parameters</span></span>  
 `pLockCount`  
 <span data-ttu-id="9de65-106">out Numero di blocchi conservati nell'attività al momento della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="9de65-106">[out] The number of locks held on the task at the time of the method call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9de65-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9de65-107">Return Value</span></span>  
  
|<span data-ttu-id="9de65-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9de65-108">HRESULT</span></span>|<span data-ttu-id="9de65-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9de65-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9de65-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9de65-110">S_OK</span></span>|<span data-ttu-id="9de65-111">`LocksHeld` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9de65-111">`LocksHeld` returned successfully.</span></span>|  
|<span data-ttu-id="9de65-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9de65-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9de65-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="9de65-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9de65-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9de65-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9de65-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9de65-115">The call timed out.</span></span>|  
|<span data-ttu-id="9de65-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9de65-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9de65-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="9de65-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9de65-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9de65-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9de65-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="9de65-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9de65-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9de65-120">E_FAIL</span></span>|<span data-ttu-id="9de65-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="9de65-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9de65-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="9de65-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9de65-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9de65-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9de65-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9de65-124">Requirements</span></span>  
 <span data-ttu-id="9de65-125">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9de65-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9de65-126">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9de65-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9de65-127">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9de65-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9de65-128">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9de65-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9de65-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9de65-129">See also</span></span>

- [<span data-ttu-id="9de65-130">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="9de65-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="9de65-131">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="9de65-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="9de65-132">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="9de65-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="9de65-133">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="9de65-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

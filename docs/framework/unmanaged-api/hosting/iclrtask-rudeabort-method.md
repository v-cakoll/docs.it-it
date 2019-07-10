---
title: Metodo ICLRTask::RudeAbort
ms.date: 03/30/2017
api_name:
- ICLRTask.RudeAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::RudeAbort
helpviewer_keywords:
- RudeAbort method, ICLRTask interface [.NET Framework hosting]
- ICLRTask::RudeAbort method [.NET Framework hosting]
ms.assetid: b5785468-fcd7-4cc3-8a5d-8796337b53fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e7750d50b772ff17cf9dcd05de2e2f34556714e4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770471"
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="01c52-102">Metodo ICLRTask::RudeAbort</span><span class="sxs-lookup"><span data-stu-id="01c52-102">ICLRTask::RudeAbort Method</span></span>
<span data-ttu-id="01c52-103">Indica a common language runtime (CLR) di interrompere l'attività rappresentata dall'oggetto corrente [interfaccia ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanze immediatamente e in modo incondizionato.</span><span class="sxs-lookup"><span data-stu-id="01c52-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01c52-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="01c52-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();   
```  
  
## <a name="return-value"></a><span data-ttu-id="01c52-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="01c52-105">Return Value</span></span>  
  
|<span data-ttu-id="01c52-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="01c52-106">HRESULT</span></span>|<span data-ttu-id="01c52-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01c52-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="01c52-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="01c52-108">S_OK</span></span>|<span data-ttu-id="01c52-109">`RudeAbort` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="01c52-109">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="01c52-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="01c52-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="01c52-111">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="01c52-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="01c52-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="01c52-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="01c52-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="01c52-113">The call timed out.</span></span>|  
|<span data-ttu-id="01c52-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="01c52-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="01c52-115">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="01c52-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="01c52-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="01c52-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="01c52-117">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="01c52-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="01c52-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="01c52-118">E_FAIL</span></span>|<span data-ttu-id="01c52-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="01c52-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="01c52-120">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="01c52-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="01c52-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="01c52-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01c52-122">Note</span><span class="sxs-lookup"><span data-stu-id="01c52-122">Remarks</span></span>  
 <span data-ttu-id="01c52-123">Un host chiama `RudeAbort` da interrompere immediatamente un'attività.</span><span class="sxs-lookup"><span data-stu-id="01c52-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="01c52-124">I finalizzatori e routine di gestione delle eccezioni non è garantiti a essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="01c52-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01c52-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="01c52-125">Requirements</span></span>  
 <span data-ttu-id="01c52-126">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01c52-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01c52-127">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="01c52-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="01c52-128">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="01c52-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01c52-129">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01c52-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01c52-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01c52-130">See also</span></span>

- [<span data-ttu-id="01c52-131">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="01c52-131">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="01c52-132">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="01c52-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="01c52-133">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="01c52-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="01c52-134">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="01c52-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

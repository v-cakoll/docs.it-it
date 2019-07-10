---
title: Metodo ICLRTask::ExitTask
ms.date: 03/30/2017
api_name:
- ICLRTask.ExitTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::ExitTask
helpviewer_keywords:
- ExitTask method [.NET Framework hosting]
- ICLRTask::ExitTask method [.NET Framework hosting]
ms.assetid: 746c85a6-4b33-4f72-a2e9-379fdf2e96af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 81afc2aa738c719456091c3f28f3ca33682776e4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759014"
---
# <a name="iclrtaskexittask-method"></a><span data-ttu-id="63d8c-102">Metodo ICLRTask::ExitTask</span><span class="sxs-lookup"><span data-stu-id="63d8c-102">ICLRTask::ExitTask Method</span></span>
<span data-ttu-id="63d8c-103">Notifica a common language runtime (CLR) che l'attività rappresentata dall'oggetto corrente [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanza sta terminando e tenta di arresto normale di attività.</span><span class="sxs-lookup"><span data-stu-id="63d8c-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is ending, and attempts to shut the task down gracefully.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63d8c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="63d8c-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="63d8c-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="63d8c-105">Return Value</span></span>  
  
|<span data-ttu-id="63d8c-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="63d8c-106">HRESULT</span></span>|<span data-ttu-id="63d8c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="63d8c-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="63d8c-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="63d8c-108">S_OK</span></span>|<span data-ttu-id="63d8c-109">`ExitTask` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="63d8c-109">`ExitTask` returned successfully.</span></span>|  
|<span data-ttu-id="63d8c-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="63d8c-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="63d8c-111">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="63d8c-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="63d8c-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="63d8c-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="63d8c-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="63d8c-113">The call timed out.</span></span>|  
|<span data-ttu-id="63d8c-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="63d8c-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="63d8c-115">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="63d8c-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="63d8c-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="63d8c-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="63d8c-117">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="63d8c-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="63d8c-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="63d8c-118">E_FAIL</span></span>|<span data-ttu-id="63d8c-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="63d8c-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="63d8c-120">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="63d8c-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="63d8c-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="63d8c-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63d8c-122">Note</span><span class="sxs-lookup"><span data-stu-id="63d8c-122">Remarks</span></span>  
 <span data-ttu-id="63d8c-123">`ExitTask` prova una chiusura normale di un'attività, in modo analogo alla disconnessione di un thread da una libreria dei tipi non gestiti.</span><span class="sxs-lookup"><span data-stu-id="63d8c-123">`ExitTask` attempts a clean shutdown of a task, in a manner analogous to detaching a thread from an unmanaged type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63d8c-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="63d8c-124">Requirements</span></span>  
 <span data-ttu-id="63d8c-125">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63d8c-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63d8c-126">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="63d8c-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="63d8c-127">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="63d8c-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="63d8c-128">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63d8c-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63d8c-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63d8c-129">See also</span></span>

- [<span data-ttu-id="63d8c-130">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="63d8c-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="63d8c-131">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="63d8c-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="63d8c-132">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="63d8c-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="63d8c-133">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="63d8c-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

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
ms.openlocfilehash: 6a55b62c7c71510435b980a4e5938c20628046f4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763633"
---
# <a name="iclrtaskexittask-method"></a><span data-ttu-id="8ea1d-102">Metodo ICLRTask::ExitTask</span><span class="sxs-lookup"><span data-stu-id="8ea1d-102">ICLRTask::ExitTask Method</span></span>
<span data-ttu-id="8ea1d-103">Notifica a common language runtime (CLR) che l'attività rappresentata dall'oggetto corrente [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanza sta terminando e tenta di arresto normale di attività.</span><span class="sxs-lookup"><span data-stu-id="8ea1d-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is ending, and attempts to shut the task down gracefully.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ea1d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8ea1d-104">Syntax</span></span>  
  
```  
HRESULT ExitTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8ea1d-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8ea1d-105">Return Value</span></span>  
  
|<span data-ttu-id="8ea1d-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8ea1d-106">HRESULT</span></span>|<span data-ttu-id="8ea1d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8ea1d-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8ea1d-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="8ea1d-108">S_OK</span></span>|<span data-ttu-id="8ea1d-109">`ExitTask` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="8ea1d-109">`ExitTask` returned successfully.</span></span>|  
|<span data-ttu-id="8ea1d-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8ea1d-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8ea1d-111">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="8ea1d-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8ea1d-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8ea1d-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8ea1d-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="8ea1d-113">The call timed out.</span></span>|  
|<span data-ttu-id="8ea1d-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8ea1d-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8ea1d-115">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="8ea1d-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8ea1d-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8ea1d-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8ea1d-117">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="8ea1d-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8ea1d-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8ea1d-118">E_FAIL</span></span>|<span data-ttu-id="8ea1d-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="8ea1d-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8ea1d-120">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="8ea1d-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8ea1d-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8ea1d-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ea1d-122">Note</span><span class="sxs-lookup"><span data-stu-id="8ea1d-122">Remarks</span></span>  
 <span data-ttu-id="8ea1d-123">`ExitTask` prova una chiusura normale di un'attività, in modo analogo alla disconnessione di un thread da una libreria dei tipi non gestiti.</span><span class="sxs-lookup"><span data-stu-id="8ea1d-123">`ExitTask` attempts a clean shutdown of a task, in a manner analogous to detaching a thread from an unmanaged type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ea1d-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8ea1d-124">Requirements</span></span>  
 <span data-ttu-id="8ea1d-125">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ea1d-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ea1d-126">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8ea1d-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8ea1d-127">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="8ea1d-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8ea1d-128">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ea1d-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ea1d-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ea1d-129">See also</span></span>

- [<span data-ttu-id="8ea1d-130">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="8ea1d-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="8ea1d-131">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="8ea1d-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="8ea1d-132">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="8ea1d-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="8ea1d-133">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="8ea1d-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

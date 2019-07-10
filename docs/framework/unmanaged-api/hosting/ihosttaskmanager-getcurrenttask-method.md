---
title: Metodo IHostTaskManager::GetCurrentTask
ms.date: 03/30/2017
api_name:
- IHostTaskManager.GetCurrentTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: f17bca49-90bd-4dee-a5e1-b9a57ea46f85
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb3044927e0d9975ed9347cd4f4896b3b75d3e29
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749629"
---
# <a name="ihosttaskmanagergetcurrenttask-method"></a><span data-ttu-id="85ce1-102">Metodo IHostTaskManager::GetCurrentTask</span><span class="sxs-lookup"><span data-stu-id="85ce1-102">IHostTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="85ce1-103">Ottiene un puntatore a interfaccia per l'attività attualmente in esecuzione nel thread del sistema operativo da cui viene effettuata la chiamata.</span><span class="sxs-lookup"><span data-stu-id="85ce1-103">Gets an interface pointer to the task that is currently executing on the operating system thread from which this call is made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85ce1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="85ce1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTask (  
    [out] IHostTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85ce1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="85ce1-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="85ce1-106">[out] Un puntatore all'indirizzo di un [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) istanza che rappresenta l'attività attualmente in esecuzione, o null, se nessuna attività è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="85ce1-106">[out] A pointer to the address of an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that represents the currently executing task, or null, if no task is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="85ce1-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="85ce1-107">Return Value</span></span>  
  
|<span data-ttu-id="85ce1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="85ce1-108">HRESULT</span></span>|<span data-ttu-id="85ce1-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="85ce1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="85ce1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="85ce1-110">S_OK</span></span>|<span data-ttu-id="85ce1-111">`GetCurrentTask` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="85ce1-111">`GetCurrentTask` returned successfully.</span></span>|  
|<span data-ttu-id="85ce1-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="85ce1-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="85ce1-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="85ce1-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="85ce1-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="85ce1-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="85ce1-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="85ce1-115">The call timed out.</span></span>|  
|<span data-ttu-id="85ce1-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="85ce1-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="85ce1-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="85ce1-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="85ce1-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="85ce1-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="85ce1-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="85ce1-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="85ce1-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="85ce1-120">E_FAIL</span></span>|<span data-ttu-id="85ce1-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="85ce1-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="85ce1-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="85ce1-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="85ce1-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="85ce1-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="85ce1-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="85ce1-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="85ce1-125">`GetCurrentTask` è stato chiamato su un thread del sistema operativo all'esterno del controllo dell'host.</span><span class="sxs-lookup"><span data-stu-id="85ce1-125">`GetCurrentTask` was called on an operating system thread outside the control of the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85ce1-126">Note</span><span class="sxs-lookup"><span data-stu-id="85ce1-126">Remarks</span></span>  
 <span data-ttu-id="85ce1-127">L'host può anche impostare il `pTask` parametro su null per impedire che un'attività che non è stata avviata il CLR.</span><span class="sxs-lookup"><span data-stu-id="85ce1-127">The host can also set the `pTask` parameter to null to prevent a task that it did not initiate from entering the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85ce1-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="85ce1-128">Requirements</span></span>  
 <span data-ttu-id="85ce1-129">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85ce1-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85ce1-130">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="85ce1-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="85ce1-131">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="85ce1-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="85ce1-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85ce1-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85ce1-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85ce1-133">See also</span></span>

- [<span data-ttu-id="85ce1-134">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="85ce1-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="85ce1-135">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="85ce1-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="85ce1-136">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="85ce1-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="85ce1-137">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="85ce1-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

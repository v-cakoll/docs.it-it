---
title: Metodo ICLRTaskManager::GetCurrentTask
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.GetCurrentTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, ICLRTaskManager interface [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: c0b82a9f-edc6-4878-9c81-48de53c02142
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9996b1a84a5f095cf12d74d0c6f594911e7a7788
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770205"
---
# <a name="iclrtaskmanagergetcurrenttask-method"></a><span data-ttu-id="5d1ad-102">Metodo ICLRTaskManager::GetCurrentTask</span><span class="sxs-lookup"><span data-stu-id="5d1ad-102">ICLRTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="5d1ad-103">Ottiene il [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanza attualmente in esecuzione nel thread del sistema operativo da cui ha avuto origine la chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-103">Gets the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance that is currently running on the operating system thread from which the method call originated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d1ad-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5d1ad-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTask (  
    [out] ICLRTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d1ad-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5d1ad-105">Parameters</span></span>  
 `ppTask`  
 <span data-ttu-id="5d1ad-106">[out] Un puntatore all'indirizzo di un `ICLRTask` istanza attualmente in esecuzione nel thread del sistema operativo da cui ha avuto origine la chiamata o null se nessuna attività è in esecuzione su questo thread.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-106">[out] A pointer to the address of an `ICLRTask` instance that is currently executing on the operating system thread from which the call originated, or null if no task is currently executing on this thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d1ad-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5d1ad-107">Return Value</span></span>  
  
|<span data-ttu-id="5d1ad-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5d1ad-108">HRESULT</span></span>|<span data-ttu-id="5d1ad-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d1ad-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5d1ad-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5d1ad-110">S_OK</span></span>|<span data-ttu-id="5d1ad-111">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="5d1ad-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5d1ad-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5d1ad-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5d1ad-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5d1ad-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5d1ad-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-115">The call timed out.</span></span>|  
|<span data-ttu-id="5d1ad-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5d1ad-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5d1ad-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5d1ad-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5d1ad-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5d1ad-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5d1ad-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5d1ad-120">E_FAIL</span></span>|<span data-ttu-id="5d1ad-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5d1ad-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5d1ad-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d1ad-124">Note</span><span class="sxs-lookup"><span data-stu-id="5d1ad-124">Remarks</span></span>  
 <span data-ttu-id="5d1ad-125">Il `ICLRTask` dell'istanza che il `ppTask` punta il parametro rappresenta l'attività attualmente in esecuzione per il CLR.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-125">The `ICLRTask` instance that the `ppTask` parameter points to represents the currently executing task for the CLR.</span></span> <span data-ttu-id="5d1ad-126">Il `ICLRTask` è associata una corrispondente istanza [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) istanza che rappresenta l'attività per l'host.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-126">The `ICLRTask` instance is associated with a corresponding [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that represents the task for the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d1ad-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5d1ad-127">Requirements</span></span>  
 <span data-ttu-id="5d1ad-128">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d1ad-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d1ad-129">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5d1ad-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5d1ad-130">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="5d1ad-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5d1ad-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d1ad-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d1ad-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d1ad-132">See also</span></span>

- [<span data-ttu-id="5d1ad-133">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="5d1ad-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="5d1ad-134">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="5d1ad-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="5d1ad-135">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="5d1ad-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="5d1ad-136">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="5d1ad-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

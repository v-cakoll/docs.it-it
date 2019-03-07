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
ms.openlocfilehash: c2efc8e0b47e68e53858bc949e6f0d0ca1352c7e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501585"
---
# <a name="iclrtaskmanagergetcurrenttask-method"></a><span data-ttu-id="3705e-102">Metodo ICLRTaskManager::GetCurrentTask</span><span class="sxs-lookup"><span data-stu-id="3705e-102">ICLRTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="3705e-103">Ottiene il [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanza attualmente in esecuzione nel thread del sistema operativo da cui ha avuto origine la chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="3705e-103">Gets the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance that is currently running on the operating system thread from which the method call originated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3705e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3705e-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentTask (  
    [out] ICLRTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3705e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3705e-105">Parameters</span></span>  
 `ppTask`  
 <span data-ttu-id="3705e-106">[out] Un puntatore all'indirizzo di un `ICLRTask` istanza attualmente in esecuzione nel thread del sistema operativo da cui ha avuto origine la chiamata o null se nessuna attività è in esecuzione su questo thread.</span><span class="sxs-lookup"><span data-stu-id="3705e-106">[out] A pointer to the address of an `ICLRTask` instance that is currently executing on the operating system thread from which the call originated, or null if no task is currently executing on this thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3705e-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3705e-107">Return Value</span></span>  
  
|<span data-ttu-id="3705e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3705e-108">HRESULT</span></span>|<span data-ttu-id="3705e-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3705e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3705e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3705e-110">S_OK</span></span>|<span data-ttu-id="3705e-111">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="3705e-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="3705e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3705e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3705e-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="3705e-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3705e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3705e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3705e-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="3705e-115">The call timed out.</span></span>|  
|<span data-ttu-id="3705e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3705e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3705e-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="3705e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3705e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3705e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3705e-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="3705e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3705e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3705e-120">E_FAIL</span></span>|<span data-ttu-id="3705e-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="3705e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3705e-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="3705e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3705e-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3705e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3705e-124">Note</span><span class="sxs-lookup"><span data-stu-id="3705e-124">Remarks</span></span>  
 <span data-ttu-id="3705e-125">Il `ICLRTask` dell'istanza che il `ppTask` punta il parametro rappresenta l'attività attualmente in esecuzione per il CLR.</span><span class="sxs-lookup"><span data-stu-id="3705e-125">The `ICLRTask` instance that the `ppTask` parameter points to represents the currently executing task for the CLR.</span></span> <span data-ttu-id="3705e-126">Il `ICLRTask` è associata una corrispondente istanza [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) istanza che rappresenta l'attività per l'host.</span><span class="sxs-lookup"><span data-stu-id="3705e-126">The `ICLRTask` instance is associated with a corresponding [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that represents the task for the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3705e-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3705e-127">Requirements</span></span>  
 <span data-ttu-id="3705e-128">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3705e-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3705e-129">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3705e-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3705e-130">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="3705e-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3705e-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3705e-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3705e-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3705e-132">See also</span></span>
- [<span data-ttu-id="3705e-133">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="3705e-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="3705e-134">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="3705e-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="3705e-135">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="3705e-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="3705e-136">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="3705e-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

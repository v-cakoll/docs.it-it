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
ms.openlocfilehash: 2420ddb5cf9be2cfb08f89d27d9aa277305e7ffb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442692"
---
# <a name="ihosttaskmanagergetcurrenttask-method"></a><span data-ttu-id="3d5df-102">Metodo IHostTaskManager::GetCurrentTask</span><span class="sxs-lookup"><span data-stu-id="3d5df-102">IHostTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="3d5df-103">Ottiene un puntatore a interfaccia per l'attività attualmente in esecuzione sul thread del sistema operativo da cui viene effettuata la chiamata.</span><span class="sxs-lookup"><span data-stu-id="3d5df-103">Gets an interface pointer to the task that is currently executing on the operating system thread from which this call is made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d5df-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3d5df-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentTask (  
    [out] IHostTask **pTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3d5df-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3d5df-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="3d5df-106">[out] Un puntatore all'indirizzo di un [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) istanza che rappresenta l'attività attualmente in esecuzione, o null, se nessuna attività è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3d5df-106">[out] A pointer to the address of an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that represents the currently executing task, or null, if no task is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3d5df-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3d5df-107">Return Value</span></span>  
  
|<span data-ttu-id="3d5df-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3d5df-108">HRESULT</span></span>|<span data-ttu-id="3d5df-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3d5df-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3d5df-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3d5df-110">S_OK</span></span>|<span data-ttu-id="3d5df-111">`GetCurrentTask` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="3d5df-111">`GetCurrentTask` returned successfully.</span></span>|  
|<span data-ttu-id="3d5df-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3d5df-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3d5df-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="3d5df-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3d5df-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3d5df-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3d5df-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="3d5df-115">The call timed out.</span></span>|  
|<span data-ttu-id="3d5df-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3d5df-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3d5df-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="3d5df-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3d5df-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3d5df-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3d5df-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="3d5df-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3d5df-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3d5df-120">E_FAIL</span></span>|<span data-ttu-id="3d5df-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="3d5df-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3d5df-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="3d5df-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3d5df-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3d5df-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3d5df-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="3d5df-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="3d5df-125">`GetCurrentTask` è stato chiamato su un thread del sistema operativo all'esterno del controllo dell'host.</span><span class="sxs-lookup"><span data-stu-id="3d5df-125">`GetCurrentTask` was called on an operating system thread outside the control of the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d5df-126">Note</span><span class="sxs-lookup"><span data-stu-id="3d5df-126">Remarks</span></span>  
 <span data-ttu-id="3d5df-127">L'host può anche impostare il `pTask` parametro su null per impedire che un'attività che non rientrano nel CLR.</span><span class="sxs-lookup"><span data-stu-id="3d5df-127">The host can also set the `pTask` parameter to null to prevent a task that it did not initiate from entering the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d5df-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3d5df-128">Requirements</span></span>  
 <span data-ttu-id="3d5df-129">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d5df-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d5df-130">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="3d5df-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3d5df-131">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="3d5df-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3d5df-132">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d5df-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d5df-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d5df-133">See Also</span></span>  
 [<span data-ttu-id="3d5df-134">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="3d5df-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="3d5df-135">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="3d5df-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="3d5df-136">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="3d5df-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="3d5df-137">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="3d5df-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

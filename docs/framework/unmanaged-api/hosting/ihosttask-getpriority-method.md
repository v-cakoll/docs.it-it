---
title: Metodo IHostTask::GetPriority
ms.date: 03/30/2017
api_name:
- IHostTask.GetPriority
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::GetPriority
helpviewer_keywords:
- GetPriority method [.NET Framework hosting]
- IHostTask::GetPriority method [.NET Framework hosting]
ms.assetid: 4b463cd6-77c1-4f9a-8518-346ad8fc4b70
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45597f6bb5e050f4afc00bd8f2db8116b29b8d4b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57482223"
---
# <a name="ihosttaskgetpriority-method"></a><span data-ttu-id="e1311-102">Metodo IHostTask::GetPriority</span><span class="sxs-lookup"><span data-stu-id="e1311-102">IHostTask::GetPriority Method</span></span>
<span data-ttu-id="e1311-103">Ottiene il livello di priorità di thread per l'attività rappresentata dall'oggetto corrente [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) istanza.</span><span class="sxs-lookup"><span data-stu-id="e1311-103">Gets the thread priority level of the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1311-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e1311-104">Syntax</span></span>  
  
```  
HRESULT GetPriority (  
    [out] int *pPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1311-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e1311-105">Parameters</span></span>  
 `pPriority`  
 <span data-ttu-id="e1311-106">[out] Un puntatore a un intero che indica il livello di priorità di thread per l'attività rappresentata dall'oggetto corrente `IHostTask` istanza.</span><span class="sxs-lookup"><span data-stu-id="e1311-106">[out] A pointer to an integer that indicates the thread priority level of the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e1311-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e1311-107">Return Value</span></span>  
  
|<span data-ttu-id="e1311-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e1311-108">HRESULT</span></span>|<span data-ttu-id="e1311-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e1311-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e1311-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e1311-110">S_OK</span></span>|<span data-ttu-id="e1311-111">`GetPriority` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="e1311-111">`GetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="e1311-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e1311-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e1311-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="e1311-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e1311-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e1311-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e1311-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="e1311-115">The call timed out.</span></span>|  
|<span data-ttu-id="e1311-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e1311-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e1311-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="e1311-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e1311-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e1311-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e1311-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="e1311-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e1311-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e1311-120">E_FAIL</span></span>|<span data-ttu-id="e1311-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="e1311-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e1311-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="e1311-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e1311-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e1311-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1311-124">Note</span><span class="sxs-lookup"><span data-stu-id="e1311-124">Remarks</span></span>  
 <span data-ttu-id="e1311-125">I valori del livello di priorità del thread vengono definiti da Win32 `SetThreadPriority` (funzione).</span><span class="sxs-lookup"><span data-stu-id="e1311-125">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1311-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e1311-126">Requirements</span></span>  
 <span data-ttu-id="e1311-127">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1311-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1311-128">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e1311-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e1311-129">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="e1311-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e1311-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1311-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1311-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1311-131">See also</span></span>
- [<span data-ttu-id="e1311-132">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="e1311-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="e1311-133">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="e1311-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="e1311-134">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="e1311-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="e1311-135">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="e1311-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

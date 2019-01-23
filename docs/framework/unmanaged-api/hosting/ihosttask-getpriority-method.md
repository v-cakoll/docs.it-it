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
ms.openlocfilehash: b832ad489c051c3422dc881c5dff31e1726ce9a5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54531278"
---
# <a name="ihosttaskgetpriority-method"></a><span data-ttu-id="d47a5-102">Metodo IHostTask::GetPriority</span><span class="sxs-lookup"><span data-stu-id="d47a5-102">IHostTask::GetPriority Method</span></span>
<span data-ttu-id="d47a5-103">Ottiene il livello di priorità di thread per l'attività rappresentata dall'oggetto corrente [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) istanza.</span><span class="sxs-lookup"><span data-stu-id="d47a5-103">Gets the thread priority level of the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d47a5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d47a5-104">Syntax</span></span>  
  
```  
HRESULT GetPriority (  
    [out] int *pPriority  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d47a5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d47a5-105">Parameters</span></span>  
 `pPriority`  
 <span data-ttu-id="d47a5-106">[out] Un puntatore a un intero che indica il livello di priorità di thread per l'attività rappresentata dall'oggetto corrente `IHostTask` istanza.</span><span class="sxs-lookup"><span data-stu-id="d47a5-106">[out] A pointer to an integer that indicates the thread priority level of the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d47a5-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d47a5-107">Return Value</span></span>  
  
|<span data-ttu-id="d47a5-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d47a5-108">HRESULT</span></span>|<span data-ttu-id="d47a5-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d47a5-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d47a5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d47a5-110">S_OK</span></span>|<span data-ttu-id="d47a5-111">`GetPriority` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="d47a5-111">`GetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="d47a5-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d47a5-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d47a5-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="d47a5-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d47a5-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d47a5-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d47a5-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="d47a5-115">The call timed out.</span></span>|  
|<span data-ttu-id="d47a5-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d47a5-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d47a5-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="d47a5-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d47a5-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d47a5-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d47a5-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="d47a5-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d47a5-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d47a5-120">E_FAIL</span></span>|<span data-ttu-id="d47a5-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="d47a5-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d47a5-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="d47a5-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d47a5-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d47a5-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d47a5-124">Note</span><span class="sxs-lookup"><span data-stu-id="d47a5-124">Remarks</span></span>  
 <span data-ttu-id="d47a5-125">I valori del livello di priorità del thread vengono definiti da Win32 `SetThreadPriority` (funzione).</span><span class="sxs-lookup"><span data-stu-id="d47a5-125">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d47a5-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d47a5-126">Requirements</span></span>  
 <span data-ttu-id="d47a5-127">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d47a5-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d47a5-128">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d47a5-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d47a5-129">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d47a5-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d47a5-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d47a5-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d47a5-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d47a5-131">See also</span></span>
- [<span data-ttu-id="d47a5-132">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="d47a5-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="d47a5-133">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="d47a5-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="d47a5-134">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="d47a5-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="d47a5-135">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="d47a5-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

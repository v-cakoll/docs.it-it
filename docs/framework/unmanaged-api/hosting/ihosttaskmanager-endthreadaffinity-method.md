---
title: Metodo IHostTaskManager::EndThreadAffinity
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EndThreadAffinity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EndThreadAffinity
helpviewer_keywords:
- EndThreadAffinity method [.NET Framework hosting]
- IHostTaskManager::EndThreadAffinity method [.NET Framework hosting]
ms.assetid: 7738a904-0cd7-4fde-a3eb-2323a5533157
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f94f365aa8c9221c64e9611deab3597e06ed862
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59157898"
---
# <a name="ihosttaskmanagerendthreadaffinity-method"></a><span data-ttu-id="e3719-102">Metodo IHostTaskManager::EndThreadAffinity</span><span class="sxs-lookup"><span data-stu-id="e3719-102">IHostTaskManager::EndThreadAffinity Method</span></span>
<span data-ttu-id="e3719-103">Notifica all'host che il codice gestito è uscendo dalla fase in cui l'attività corrente non deve essere spostato a un altro thread del sistema operativo, seguendo una precedente chiamata a [BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md).</span><span class="sxs-lookup"><span data-stu-id="e3719-103">Notifies the host that managed code is exiting the period in which the current task must not be moved to another operating system thread, following an earlier call to [IHostTaskManager::BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3719-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e3719-104">Syntax</span></span>  
  
```  
HRESULT EndThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e3719-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e3719-105">Return Value</span></span>  
  
|<span data-ttu-id="e3719-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e3719-106">HRESULT</span></span>|<span data-ttu-id="e3719-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e3719-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e3719-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="e3719-108">S_OK</span></span>|<span data-ttu-id="e3719-109">`EndThreadAffinity` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="e3719-109">`EndThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="e3719-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e3719-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e3719-111">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="e3719-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e3719-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e3719-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e3719-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="e3719-113">The call timed out.</span></span>|  
|<span data-ttu-id="e3719-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e3719-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e3719-115">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="e3719-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e3719-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e3719-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e3719-117">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="e3719-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e3719-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e3719-118">E_FAIL</span></span>|<span data-ttu-id="e3719-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="e3719-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e3719-120">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="e3719-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e3719-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e3719-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e3719-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="e3719-122">E_UNEXPECTED</span></span>|<span data-ttu-id="e3719-123">`EndThreadAffinity` è stato chiamato senza una chiamata corrispondente a `BeginThreadAffinity`.</span><span class="sxs-lookup"><span data-stu-id="e3719-123">`EndThreadAffinity` was called without an earlier corresponding call to `BeginThreadAffinity`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3719-124">Note</span><span class="sxs-lookup"><span data-stu-id="e3719-124">Remarks</span></span>  
 <span data-ttu-id="e3719-125">Common Language Runtime effettua una chiamata corrispondente al `BeginThreadAffinity` sull'attività corrente prima di chiamare `EndThreadAffinity`.</span><span class="sxs-lookup"><span data-stu-id="e3719-125">The CLR makes a corresponding call to `BeginThreadAffinity` on the current task before calling `EndThreadAffinity`.</span></span> <span data-ttu-id="e3719-126">In assenza di una corrispondente chiamata di questo tipo, l'implementazione di host dei [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) deve restituire E_UNEXPECTED e non eseguire alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="e3719-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) should return E_UNEXPECTED, and take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3719-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e3719-127">Requirements</span></span>  
 <span data-ttu-id="e3719-128">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3719-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3719-129">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e3719-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e3719-130">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="e3719-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e3719-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3719-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3719-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3719-132">See also</span></span>

- <xref:System.Threading>
- [<span data-ttu-id="e3719-133">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="e3719-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="e3719-134">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="e3719-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="e3719-135">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="e3719-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="e3719-136">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="e3719-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

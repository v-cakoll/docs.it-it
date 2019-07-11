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
ms.openlocfilehash: b50e08e6fe0db7d16c87d9acccf77e2b15094039
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749644"
---
# <a name="ihosttaskmanagerendthreadaffinity-method"></a><span data-ttu-id="dd4e7-102">Metodo IHostTaskManager::EndThreadAffinity</span><span class="sxs-lookup"><span data-stu-id="dd4e7-102">IHostTaskManager::EndThreadAffinity Method</span></span>
<span data-ttu-id="dd4e7-103">Notifica all'host che il codice gestito è uscendo dalla fase in cui l'attività corrente non deve essere spostato a un altro thread del sistema operativo, seguendo una precedente chiamata a [BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md).</span><span class="sxs-lookup"><span data-stu-id="dd4e7-103">Notifies the host that managed code is exiting the period in which the current task must not be moved to another operating system thread, following an earlier call to [IHostTaskManager::BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd4e7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dd4e7-104">Syntax</span></span>  
  
```cpp  
HRESULT EndThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="dd4e7-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="dd4e7-105">Return Value</span></span>  
  
|<span data-ttu-id="dd4e7-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dd4e7-106">HRESULT</span></span>|<span data-ttu-id="dd4e7-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd4e7-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dd4e7-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="dd4e7-108">S_OK</span></span>|<span data-ttu-id="dd4e7-109">`EndThreadAffinity` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="dd4e7-109">`EndThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="dd4e7-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dd4e7-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dd4e7-111">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="dd4e7-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dd4e7-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dd4e7-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dd4e7-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="dd4e7-113">The call timed out.</span></span>|  
|<span data-ttu-id="dd4e7-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dd4e7-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dd4e7-115">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="dd4e7-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dd4e7-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dd4e7-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dd4e7-117">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="dd4e7-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dd4e7-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dd4e7-118">E_FAIL</span></span>|<span data-ttu-id="dd4e7-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="dd4e7-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dd4e7-120">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="dd4e7-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dd4e7-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="dd4e7-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="dd4e7-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="dd4e7-122">E_UNEXPECTED</span></span>|<span data-ttu-id="dd4e7-123">`EndThreadAffinity` è stato chiamato senza una chiamata corrispondente a `BeginThreadAffinity`.</span><span class="sxs-lookup"><span data-stu-id="dd4e7-123">`EndThreadAffinity` was called without an earlier corresponding call to `BeginThreadAffinity`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd4e7-124">Note</span><span class="sxs-lookup"><span data-stu-id="dd4e7-124">Remarks</span></span>  
 <span data-ttu-id="dd4e7-125">Common Language Runtime effettua una chiamata corrispondente al `BeginThreadAffinity` sull'attività corrente prima di chiamare `EndThreadAffinity`.</span><span class="sxs-lookup"><span data-stu-id="dd4e7-125">The CLR makes a corresponding call to `BeginThreadAffinity` on the current task before calling `EndThreadAffinity`.</span></span> <span data-ttu-id="dd4e7-126">In assenza di una corrispondente chiamata di questo tipo, l'implementazione di host dei [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) deve restituire E_UNEXPECTED e non eseguire alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="dd4e7-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) should return E_UNEXPECTED, and take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd4e7-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dd4e7-127">Requirements</span></span>  
 <span data-ttu-id="dd4e7-128">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd4e7-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd4e7-129">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dd4e7-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dd4e7-130">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="dd4e7-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dd4e7-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd4e7-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd4e7-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd4e7-132">See also</span></span>

- <xref:System.Threading>
- [<span data-ttu-id="dd4e7-133">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="dd4e7-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="dd4e7-134">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="dd4e7-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="dd4e7-135">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="dd4e7-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="dd4e7-136">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="dd4e7-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

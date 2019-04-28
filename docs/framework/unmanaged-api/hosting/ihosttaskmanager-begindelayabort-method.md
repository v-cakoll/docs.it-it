---
title: Metodo IHostTaskManager::BeginDelayAbort
ms.date: 03/30/2017
api_name:
- IHostTaskManager.BeginDelayAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::BeginDelayAbort
helpviewer_keywords:
- BeginDelayAbort method [.NET Framework hosting]
- IHostTaskManager::BeginDelayAbort method [.NET Framework hosting]
ms.assetid: 75f42a8b-ed68-4718-a030-a179cfba7d72
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 328462343669b3ea6bed2d86514ea348f6ae2b1e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789534"
---
# <a name="ihosttaskmanagerbegindelayabort-method"></a><span data-ttu-id="56ade-102">Metodo IHostTaskManager::BeginDelayAbort</span><span class="sxs-lookup"><span data-stu-id="56ade-102">IHostTaskManager::BeginDelayAbort Method</span></span>
<span data-ttu-id="56ade-103">Notifica all'host che il codice gestito sta entrando in un periodo in cui l'attività corrente non deve essere interrotta.</span><span class="sxs-lookup"><span data-stu-id="56ade-103">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56ade-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="56ade-104">Syntax</span></span>  
  
```  
HRESULT BeginDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="56ade-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="56ade-105">Return Value</span></span>  
  
|<span data-ttu-id="56ade-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="56ade-106">HRESULT</span></span>|<span data-ttu-id="56ade-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="56ade-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="56ade-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="56ade-108">S_OK</span></span>|<span data-ttu-id="56ade-109">`BeginDelayAbort` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="56ade-109">`BeginDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="56ade-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="56ade-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="56ade-111">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="56ade-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="56ade-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="56ade-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="56ade-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="56ade-113">The call timed out.</span></span>|  
|<span data-ttu-id="56ade-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="56ade-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="56ade-115">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="56ade-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="56ade-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="56ade-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="56ade-117">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="56ade-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="56ade-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="56ade-118">E_FAIL</span></span>|<span data-ttu-id="56ade-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="56ade-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="56ade-120">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="56ade-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="56ade-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="56ade-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="56ade-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="56ade-122">E_UNEXPECTED</span></span>|<span data-ttu-id="56ade-123">`BeginDelayAbort` è già stato chiamato, ma la chiamata corrispondente a [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) non è ancora stato ricevuto.</span><span class="sxs-lookup"><span data-stu-id="56ade-123">`BeginDelayAbort` has already been called, but the corresponding call to [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) has not yet been received.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56ade-124">Note</span><span class="sxs-lookup"><span data-stu-id="56ade-124">Remarks</span></span>  
 <span data-ttu-id="56ade-125">L'host non deve interrompere l'attività corrente fino a `EndDelayAbort` viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="56ade-125">The host must not abort the current task until `EndDelayAbort` is called.</span></span> <span data-ttu-id="56ade-126">Se un'altra chiamata a `BeginDelayAbort` viene eseguita senza una chiamata corrispondente a `EndDelayAbort`, l'host deve restituire E_UNEXPECTED `BeginDelayAbort`e non deve eseguire alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="56ade-126">If another call to `BeginDelayAbort` is made without an intervening call to `EndDelayAbort`, the host should return E_UNEXPECTED from `BeginDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56ade-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="56ade-127">Requirements</span></span>  
 <span data-ttu-id="56ade-128">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56ade-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56ade-129">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="56ade-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="56ade-130">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="56ade-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="56ade-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56ade-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56ade-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56ade-132">See also</span></span>

- [<span data-ttu-id="56ade-133">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="56ade-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="56ade-134">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="56ade-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="56ade-135">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="56ade-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

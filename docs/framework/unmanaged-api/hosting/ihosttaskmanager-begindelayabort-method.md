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
ms.openlocfilehash: 65bb59efa9d38fa32baa38eb239103f5cfa8be86
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441916"
---
# <a name="ihosttaskmanagerbegindelayabort-method"></a><span data-ttu-id="60ea7-102">Metodo IHostTaskManager::BeginDelayAbort</span><span class="sxs-lookup"><span data-stu-id="60ea7-102">IHostTaskManager::BeginDelayAbort Method</span></span>
<span data-ttu-id="60ea7-103">Notifica all'host che il codice gestito sta entrando in un periodo in cui l'attività corrente non deve essere interrotta.</span><span class="sxs-lookup"><span data-stu-id="60ea7-103">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60ea7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="60ea7-104">Syntax</span></span>  
  
```  
HRESULT BeginDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="60ea7-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="60ea7-105">Return Value</span></span>  
  
|<span data-ttu-id="60ea7-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="60ea7-106">HRESULT</span></span>|<span data-ttu-id="60ea7-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="60ea7-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="60ea7-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="60ea7-108">S_OK</span></span>|<span data-ttu-id="60ea7-109">`BeginDelayAbort` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="60ea7-109">`BeginDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="60ea7-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="60ea7-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="60ea7-111">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="60ea7-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="60ea7-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="60ea7-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="60ea7-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="60ea7-113">The call timed out.</span></span>|  
|<span data-ttu-id="60ea7-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="60ea7-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="60ea7-115">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="60ea7-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="60ea7-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="60ea7-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="60ea7-117">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="60ea7-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="60ea7-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="60ea7-118">E_FAIL</span></span>|<span data-ttu-id="60ea7-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="60ea7-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="60ea7-120">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="60ea7-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="60ea7-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="60ea7-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="60ea7-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="60ea7-122">E_UNEXPECTED</span></span>|<span data-ttu-id="60ea7-123">`BeginDelayAbort` è già stato chiamato, ma la chiamata corrispondente a [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) non ha ancora ricevuto.</span><span class="sxs-lookup"><span data-stu-id="60ea7-123">`BeginDelayAbort` has already been called, but the corresponding call to [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) has not yet been received.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60ea7-124">Note</span><span class="sxs-lookup"><span data-stu-id="60ea7-124">Remarks</span></span>  
 <span data-ttu-id="60ea7-125">L'host non deve interrompere l'attività corrente fino a quando `EndDelayAbort` viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="60ea7-125">The host must not abort the current task until `EndDelayAbort` is called.</span></span> <span data-ttu-id="60ea7-126">Se un'altra chiamata a `BeginDelayAbort` viene eseguita senza una corrispondente chiamata a `EndDelayAbort`, l'host deve restituire E_UNEXPECTED da `BeginDelayAbort`e deve eseguire alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="60ea7-126">If another call to `BeginDelayAbort` is made without an intervening call to `EndDelayAbort`, the host should return E_UNEXPECTED from `BeginDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60ea7-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="60ea7-127">Requirements</span></span>  
 <span data-ttu-id="60ea7-128">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60ea7-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60ea7-129">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="60ea7-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="60ea7-130">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="60ea7-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="60ea7-131">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60ea7-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60ea7-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60ea7-132">See Also</span></span>  
 [<span data-ttu-id="60ea7-133">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="60ea7-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="60ea7-134">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="60ea7-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="60ea7-135">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="60ea7-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="60ea7-136">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="60ea7-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

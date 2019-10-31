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
ms.openlocfilehash: b765d5449cebbdec5f106a8e4743fee2f0ee5521
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133130"
---
# <a name="ihosttaskmanagerbegindelayabort-method"></a><span data-ttu-id="c9bcf-102">Metodo IHostTaskManager::BeginDelayAbort</span><span class="sxs-lookup"><span data-stu-id="c9bcf-102">IHostTaskManager::BeginDelayAbort Method</span></span>
<span data-ttu-id="c9bcf-103">Notifica all'host che il codice gestito sta immettendo un punto in cui l'attività corrente non deve essere interrotta.</span><span class="sxs-lookup"><span data-stu-id="c9bcf-103">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9bcf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c9bcf-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="c9bcf-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c9bcf-105">Return Value</span></span>  
  
|<span data-ttu-id="c9bcf-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c9bcf-106">HRESULT</span></span>|<span data-ttu-id="c9bcf-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c9bcf-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c9bcf-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="c9bcf-108">S_OK</span></span>|<span data-ttu-id="c9bcf-109">`BeginDelayAbort` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="c9bcf-109">`BeginDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="c9bcf-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c9bcf-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c9bcf-111">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="c9bcf-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c9bcf-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c9bcf-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c9bcf-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="c9bcf-113">The call timed out.</span></span>|  
|<span data-ttu-id="c9bcf-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c9bcf-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c9bcf-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="c9bcf-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c9bcf-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c9bcf-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c9bcf-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="c9bcf-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c9bcf-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c9bcf-118">E_FAIL</span></span>|<span data-ttu-id="c9bcf-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="c9bcf-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c9bcf-120">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="c9bcf-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c9bcf-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c9bcf-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c9bcf-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="c9bcf-122">E_UNEXPECTED</span></span>|<span data-ttu-id="c9bcf-123">`BeginDelayAbort` è già stato chiamato, ma non è stata ancora ricevuta la chiamata corrispondente a [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c9bcf-123">`BeginDelayAbort` has already been called, but the corresponding call to [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) has not yet been received.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9bcf-124">Note</span><span class="sxs-lookup"><span data-stu-id="c9bcf-124">Remarks</span></span>  
 <span data-ttu-id="c9bcf-125">L'host non deve interrompere l'attività corrente fino a quando non viene chiamato `EndDelayAbort`.</span><span class="sxs-lookup"><span data-stu-id="c9bcf-125">The host must not abort the current task until `EndDelayAbort` is called.</span></span> <span data-ttu-id="c9bcf-126">Se un'altra chiamata a `BeginDelayAbort` viene effettuata senza una chiamata corrispondente a `EndDelayAbort`, l'host deve restituire E_UNEXPECTED da `BeginDelayAbort`e non deve eseguire alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="c9bcf-126">If another call to `BeginDelayAbort` is made without an intervening call to `EndDelayAbort`, the host should return E_UNEXPECTED from `BeginDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9bcf-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c9bcf-127">Requirements</span></span>  
 <span data-ttu-id="c9bcf-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9bcf-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9bcf-129">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c9bcf-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c9bcf-130">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c9bcf-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c9bcf-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9bcf-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9bcf-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9bcf-132">See also</span></span>

- [<span data-ttu-id="c9bcf-133">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="c9bcf-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="c9bcf-134">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="c9bcf-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="c9bcf-135">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="c9bcf-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

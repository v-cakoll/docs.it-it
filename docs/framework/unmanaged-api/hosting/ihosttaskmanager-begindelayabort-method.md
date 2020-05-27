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
ms.openlocfilehash: ea3269d06fdd3f5a2e365465d45ba6e569127b0a
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842374"
---
# <a name="ihosttaskmanagerbegindelayabort-method"></a><span data-ttu-id="cfa62-102">Metodo IHostTaskManager::BeginDelayAbort</span><span class="sxs-lookup"><span data-stu-id="cfa62-102">IHostTaskManager::BeginDelayAbort Method</span></span>
<span data-ttu-id="cfa62-103">Notifica all'host che il codice gestito sta immettendo un punto in cui l'attività corrente non deve essere interrotta.</span><span class="sxs-lookup"><span data-stu-id="cfa62-103">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfa62-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cfa62-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="cfa62-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="cfa62-105">Return Value</span></span>  
  
|<span data-ttu-id="cfa62-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cfa62-106">HRESULT</span></span>|<span data-ttu-id="cfa62-107">Description</span><span class="sxs-lookup"><span data-stu-id="cfa62-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cfa62-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="cfa62-108">S_OK</span></span>|<span data-ttu-id="cfa62-109">`BeginDelayAbort`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="cfa62-109">`BeginDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="cfa62-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cfa62-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cfa62-111">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="cfa62-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cfa62-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cfa62-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cfa62-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="cfa62-113">The call timed out.</span></span>|  
|<span data-ttu-id="cfa62-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cfa62-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cfa62-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="cfa62-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cfa62-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cfa62-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cfa62-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="cfa62-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cfa62-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cfa62-118">E_FAIL</span></span>|<span data-ttu-id="cfa62-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="cfa62-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cfa62-120">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="cfa62-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cfa62-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="cfa62-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="cfa62-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="cfa62-122">E_UNEXPECTED</span></span>|<span data-ttu-id="cfa62-123">`BeginDelayAbort`è già stato chiamato, ma non è stata ancora ricevuta la chiamata corrispondente a [EndDelayAbort](ihosttaskmanager-enddelayabort-method.md) .</span><span class="sxs-lookup"><span data-stu-id="cfa62-123">`BeginDelayAbort` has already been called, but the corresponding call to [EndDelayAbort](ihosttaskmanager-enddelayabort-method.md) has not yet been received.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cfa62-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="cfa62-124">Remarks</span></span>  
 <span data-ttu-id="cfa62-125">L'host non deve interrompere l'attività corrente fino a quando non `EndDelayAbort` viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="cfa62-125">The host must not abort the current task until `EndDelayAbort` is called.</span></span> <span data-ttu-id="cfa62-126">Se un'altra chiamata a `BeginDelayAbort` viene effettuata senza una chiamata corrispondente a `EndDelayAbort` , l'host deve restituire E_UNEXPECTED da `BeginDelayAbort` e non deve eseguire alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="cfa62-126">If another call to `BeginDelayAbort` is made without an intervening call to `EndDelayAbort`, the host should return E_UNEXPECTED from `BeginDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfa62-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cfa62-127">Requirements</span></span>  
 <span data-ttu-id="cfa62-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cfa62-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfa62-129">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="cfa62-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cfa62-130">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cfa62-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cfa62-131">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfa62-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfa62-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cfa62-132">See also</span></span>

- [<span data-ttu-id="cfa62-133">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="cfa62-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="cfa62-134">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="cfa62-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="cfa62-135">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="cfa62-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)

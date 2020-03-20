---
title: Metodo ICLRTask::RudeAbort
ms.date: 03/30/2017
api_name:
- ICLRTask.RudeAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::RudeAbort
helpviewer_keywords:
- RudeAbort method, ICLRTask interface [.NET Framework hosting]
- ICLRTask::RudeAbort method [.NET Framework hosting]
ms.assetid: b5785468-fcd7-4cc3-8a5d-8796337b53fc
topic_type:
- apiref
ms.openlocfilehash: aacf9de36dc39b63ed36b672e31f40704413d608
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176331"
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="8b0a3-102">Metodo ICLRTask::RudeAbort</span><span class="sxs-lookup"><span data-stu-id="8b0a3-102">ICLRTask::RudeAbort Method</span></span>
<span data-ttu-id="8b0a3-103">Indica a Common Language Runtime (CLR) di interrompere immediatamente e incondizionatamente l'attività rappresentata dall'istanza corrente dell'interfaccia [ICLRTask.](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)</span><span class="sxs-lookup"><span data-stu-id="8b0a3-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b0a3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8b0a3-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();
```  
  
## <a name="return-value"></a><span data-ttu-id="8b0a3-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8b0a3-105">Return Value</span></span>  
  
|<span data-ttu-id="8b0a3-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8b0a3-106">HRESULT</span></span>|<span data-ttu-id="8b0a3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8b0a3-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8b0a3-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="8b0a3-108">S_OK</span></span>|<span data-ttu-id="8b0a3-109">`RudeAbort`restituito con successo.</span><span class="sxs-lookup"><span data-stu-id="8b0a3-109">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="8b0a3-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8b0a3-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8b0a3-111">CLR non è stato caricato in un processo o CLR si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="8b0a3-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8b0a3-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8b0a3-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8b0a3-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="8b0a3-113">The call timed out.</span></span>|  
|<span data-ttu-id="8b0a3-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8b0a3-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8b0a3-115">Il chiamante non è proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="8b0a3-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8b0a3-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8b0a3-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8b0a3-117">Un evento è stato annullato mentre un thread bloccato o una fibra era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="8b0a3-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8b0a3-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8b0a3-118">E_FAIL</span></span>|<span data-ttu-id="8b0a3-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="8b0a3-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8b0a3-120">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="8b0a3-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8b0a3-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8b0a3-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b0a3-122">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8b0a3-122">Remarks</span></span>  
 <span data-ttu-id="8b0a3-123">Un host `RudeAbort` chiama per interrompere immediatamente un'attività.</span><span class="sxs-lookup"><span data-stu-id="8b0a3-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="8b0a3-124">Non è garantito che i finalizzatori e le routine di gestione delle eccezioni vengano eseguiti.</span><span class="sxs-lookup"><span data-stu-id="8b0a3-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b0a3-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8b0a3-125">Requirements</span></span>  
 <span data-ttu-id="8b0a3-126">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b0a3-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b0a3-127">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8b0a3-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8b0a3-128">**Biblioteca:** Incluso come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8b0a3-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8b0a3-129">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b0a3-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b0a3-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b0a3-130">See also</span></span>

- [<span data-ttu-id="8b0a3-131">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="8b0a3-131">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="8b0a3-132">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="8b0a3-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="8b0a3-133">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="8b0a3-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="8b0a3-134">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="8b0a3-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

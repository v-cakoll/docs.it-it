---
title: Metodo ICLRTask::YieldTask
ms.date: 03/30/2017
api_name:
- ICLRTask.YieldTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::YieldTask
helpviewer_keywords:
- ICLRTask::YieldTask method [.NET Framework hosting]
- YieldTask method [.NET Framework hosting]
ms.assetid: b8eb4095-3a8f-4be3-9446-63e9893dce7d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc8d936ac4fca704e7e3069209d8ff75d46b044d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59113672"
---
# <a name="iclrtaskyieldtask-method"></a><span data-ttu-id="3f311-102">Metodo ICLRTask::YieldTask</span><span class="sxs-lookup"><span data-stu-id="3f311-102">ICLRTask::YieldTask Method</span></span>
<span data-ttu-id="3f311-103">Richiede che common language runtime (CLR) di sospendere le attività che l'oggetto corrente [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) rappresenta dell'istanza e il tempo del processore di rendere disponibile ad altre attività.</span><span class="sxs-lookup"><span data-stu-id="3f311-103">Requests that the common language runtime (CLR) put aside the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents, and make the processor time available to other tasks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f311-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3f311-104">Syntax</span></span>  
  
```  
HRESULT YieldTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3f311-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3f311-105">Return Value</span></span>  
  
|<span data-ttu-id="3f311-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3f311-106">HRESULT</span></span>|<span data-ttu-id="3f311-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3f311-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3f311-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="3f311-108">S_OK</span></span>|`YieldTask` <span data-ttu-id="3f311-109">stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="3f311-109">returned successfully.</span></span>|  
|<span data-ttu-id="3f311-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3f311-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3f311-111">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="3f311-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3f311-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3f311-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3f311-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="3f311-113">The call timed out.</span></span>|  
|<span data-ttu-id="3f311-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3f311-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3f311-115">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="3f311-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3f311-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3f311-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3f311-117">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="3f311-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3f311-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3f311-118">E_FAIL</span></span>|<span data-ttu-id="3f311-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="3f311-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3f311-120">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="3f311-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3f311-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3f311-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f311-122">Note</span><span class="sxs-lookup"><span data-stu-id="3f311-122">Remarks</span></span>  
 <span data-ttu-id="3f311-123">Un host chiama il metodo `YieldTask` per richiedere le risorse del processore per altri processi o attività.</span><span class="sxs-lookup"><span data-stu-id="3f311-123">A host calls `YieldTask` to request processor resources for other tasks or processes.</span></span> <span data-ttu-id="3f311-124">Questo metodo è destinato principalmente per consentire al codice con esecuzione prolungata concedere il tempo della CPU.</span><span class="sxs-lookup"><span data-stu-id="3f311-124">This method is primarily intended to allow long-running code to give up CPU time.</span></span> <span data-ttu-id="3f311-125">Il runtime tenta di inserire l'attività che corrente `ICLRTask` istanza rappresenta in uno stato in cui è possibile ottenere il tempo di elaborazione, ma non garantisce di successo.</span><span class="sxs-lookup"><span data-stu-id="3f311-125">The runtime attempts to put the task that the current `ICLRTask` instance represents in a state where it can yield processing time, but makes no guarantee of success.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f311-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3f311-126">Requirements</span></span>  
 <span data-ttu-id="3f311-127">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f311-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f311-128">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3f311-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3f311-129">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="3f311-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="3f311-130">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3f311-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3f311-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f311-131">See also</span></span>

- [<span data-ttu-id="3f311-132">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="3f311-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="3f311-133">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="3f311-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="3f311-134">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="3f311-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="3f311-135">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="3f311-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

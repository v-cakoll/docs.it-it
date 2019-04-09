---
title: Metodo ICLRTask::SwitchOut
ms.date: 03/30/2017
api_name:
- ICLRTask.SwitchOut
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchOut
helpviewer_keywords:
- ICLRTask::SwitchOut method [.NET Framework hosting]
- SwitchOut method [.NET Framework hosting]
ms.assetid: b6fb168c-b24b-4ecf-a390-2b5ba3317ae6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a215189461bd22011462842bf02ff6c0109119fa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090056"
---
# <a name="iclrtaskswitchout-method"></a><span data-ttu-id="810a0-102">Metodo ICLRTask::SwitchOut</span><span class="sxs-lookup"><span data-stu-id="810a0-102">ICLRTask::SwitchOut Method</span></span>
<span data-ttu-id="810a0-103">Notifica a common language runtime (CLR) che l'attività rappresentata dall'oggetto corrente [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanza non è più in uno stato eseguibile.</span><span class="sxs-lookup"><span data-stu-id="810a0-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is no longer in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="810a0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="810a0-104">Syntax</span></span>  
  
```  
HRESULT SwitchOut ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="810a0-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="810a0-105">Return Value</span></span>  
  
|<span data-ttu-id="810a0-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="810a0-106">HRESULT</span></span>|<span data-ttu-id="810a0-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="810a0-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="810a0-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="810a0-108">S_OK</span></span>|`SwitchOut` <span data-ttu-id="810a0-109">stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="810a0-109">returned successfully.</span></span>|  
|<span data-ttu-id="810a0-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="810a0-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="810a0-111">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="810a0-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="810a0-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="810a0-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="810a0-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="810a0-113">The call timed out.</span></span>|  
|<span data-ttu-id="810a0-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="810a0-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="810a0-115">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="810a0-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="810a0-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="810a0-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="810a0-117">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="810a0-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="810a0-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="810a0-118">E_FAIL</span></span>|<span data-ttu-id="810a0-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="810a0-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="810a0-120">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="810a0-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="810a0-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="810a0-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="810a0-122">Note</span><span class="sxs-lookup"><span data-stu-id="810a0-122">Remarks</span></span>  
 <span data-ttu-id="810a0-123">Un host chiama `SwitchOut` per indicare a CLR che è stata temporaneamente interrotta l'esecuzione dell'attività che corrente `ICLRTask` istanza rappresenta, quindi verrà ripianificata.</span><span class="sxs-lookup"><span data-stu-id="810a0-123">A host calls `SwitchOut` to inform the CLR that it has temporarily stopped executing the task that the current `ICLRTask` instance represents, and will reschedule the task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="810a0-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="810a0-124">Requirements</span></span>  
 <span data-ttu-id="810a0-125">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="810a0-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="810a0-126">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="810a0-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="810a0-127">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="810a0-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="810a0-128">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="810a0-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="810a0-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="810a0-129">See also</span></span>

- [<span data-ttu-id="810a0-130">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="810a0-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="810a0-131">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="810a0-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="810a0-132">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="810a0-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="810a0-133">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="810a0-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

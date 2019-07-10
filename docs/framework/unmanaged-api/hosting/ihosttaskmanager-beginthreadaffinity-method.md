---
title: Metodo IHostTaskManager::BeginThreadAffinity
ms.date: 03/30/2017
api_name:
- IHostTaskManager.BeginThreadAffinity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::BeginThreadAffinity
helpviewer_keywords:
- IHostTaskManager::BeginThreadAffinity method [.NET Framework hosting]
- BeginThreadAffinity method [.NET Framework hosting]
ms.assetid: fea3ab88-ce41-4c5a-847b-bb78cd748da6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 59af484710dc0848d7712017021adc5f3dcb7bce
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749765"
---
# <a name="ihosttaskmanagerbeginthreadaffinity-method"></a><span data-ttu-id="17921-102">Metodo IHostTaskManager::BeginThreadAffinity</span><span class="sxs-lookup"><span data-stu-id="17921-102">IHostTaskManager::BeginThreadAffinity Method</span></span>
<span data-ttu-id="17921-103">Notifica all'host che il codice gestito sta entrando in un periodo in cui l'attività corrente non deve essere spostato a un altro thread del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="17921-103">Notifies the host that managed code is entering a period in which the current task must not be moved to another operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17921-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="17921-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="17921-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="17921-105">Return Value</span></span>  
  
|<span data-ttu-id="17921-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="17921-106">HRESULT</span></span>|<span data-ttu-id="17921-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="17921-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="17921-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="17921-108">S_OK</span></span>|<span data-ttu-id="17921-109">`BeginThreadAffinity` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="17921-109">`BeginThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="17921-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="17921-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="17921-111">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="17921-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="17921-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="17921-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="17921-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="17921-113">The call timed out.</span></span>|  
|<span data-ttu-id="17921-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="17921-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="17921-115">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="17921-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="17921-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="17921-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="17921-117">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="17921-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="17921-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="17921-118">E_FAIL</span></span>|<span data-ttu-id="17921-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="17921-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="17921-120">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="17921-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="17921-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="17921-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17921-122">Note</span><span class="sxs-lookup"><span data-stu-id="17921-122">Remarks</span></span>  
 <span data-ttu-id="17921-123">CLR chiama in genere `IHostTaskManager::BeginThreadAffinity` nel contesto di una chiamata a <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="17921-123">The CLR typically calls `IHostTaskManager::BeginThreadAffinity` in the context of a call to <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="17921-124">L'attività corrente non deve essere ripianificata fino a quando non viene eseguita una chiamata corrispondente a [EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md).</span><span class="sxs-lookup"><span data-stu-id="17921-124">The current task must not be rescheduled until a corresponding call is made to [IHostTaskManager::EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md).</span></span> <span data-ttu-id="17921-125">Le attività possono essere passati all'esterno, ma quando vengono riattivate in, deve essere assegnati al thread del sistema operativo stesso da cui erano state disattivate. Annidati le chiamate a `BeginThreadAffinity` non hanno alcun effetto, poiché la chiamata si riferisce all'attività corrente.</span><span class="sxs-lookup"><span data-stu-id="17921-125">Tasks can be switched out, but when they are switched back in, they must be assigned to the same operating system thread from which they were switched out. Nested calls to `BeginThreadAffinity` have no effect, because the call refers to the current task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17921-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="17921-126">Requirements</span></span>  
 <span data-ttu-id="17921-127">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17921-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17921-128">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="17921-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="17921-129">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="17921-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="17921-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17921-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17921-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17921-131">See also</span></span>

- [<span data-ttu-id="17921-132">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="17921-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="17921-133">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="17921-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="17921-134">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="17921-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="17921-135">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="17921-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

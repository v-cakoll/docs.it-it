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
ms.openlocfilehash: 67a133604e269b8c20dc8640b91e378c498cf038
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745579"
---
# <a name="ihosttaskmanagerbeginthreadaffinity-method"></a><span data-ttu-id="f87b5-102">Metodo IHostTaskManager::BeginThreadAffinity</span><span class="sxs-lookup"><span data-stu-id="f87b5-102">IHostTaskManager::BeginThreadAffinity Method</span></span>
<span data-ttu-id="f87b5-103">Notifica all'host che il codice gestito sta entrando in un periodo in cui l'attività corrente non deve essere spostato a un altro thread del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="f87b5-103">Notifies the host that managed code is entering a period in which the current task must not be moved to another operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f87b5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f87b5-104">Syntax</span></span>  
  
```  
HRESULT BeginThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f87b5-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f87b5-105">Return Value</span></span>  
  
|<span data-ttu-id="f87b5-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f87b5-106">HRESULT</span></span>|<span data-ttu-id="f87b5-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f87b5-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f87b5-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="f87b5-108">S_OK</span></span>|<span data-ttu-id="f87b5-109">`BeginThreadAffinity` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="f87b5-109">`BeginThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="f87b5-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f87b5-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f87b5-111">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="f87b5-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f87b5-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f87b5-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f87b5-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f87b5-113">The call timed out.</span></span>|  
|<span data-ttu-id="f87b5-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f87b5-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f87b5-115">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="f87b5-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f87b5-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f87b5-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f87b5-117">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="f87b5-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f87b5-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f87b5-118">E_FAIL</span></span>|<span data-ttu-id="f87b5-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="f87b5-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f87b5-120">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="f87b5-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f87b5-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f87b5-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f87b5-122">Note</span><span class="sxs-lookup"><span data-stu-id="f87b5-122">Remarks</span></span>  
 <span data-ttu-id="f87b5-123">CLR chiama in genere `IHostTaskManager::BeginThreadAffinity` nel contesto di una chiamata a <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f87b5-123">The CLR typically calls `IHostTaskManager::BeginThreadAffinity` in the context of a call to <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f87b5-124">L'attività corrente non deve essere ripianificata fino a quando non viene eseguita una chiamata corrispondente a [EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md).</span><span class="sxs-lookup"><span data-stu-id="f87b5-124">The current task must not be rescheduled until a corresponding call is made to [IHostTaskManager::EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md).</span></span> <span data-ttu-id="f87b5-125">Le attività possono essere passati all'esterno, ma quando vengono riattivate in, deve essere assegnati al thread del sistema operativo stesso da cui erano state disattivate. Annidati le chiamate a `BeginThreadAffinity` non hanno alcun effetto, poiché la chiamata si riferisce all'attività corrente.</span><span class="sxs-lookup"><span data-stu-id="f87b5-125">Tasks can be switched out, but when they are switched back in, they must be assigned to the same operating system thread from which they were switched out. Nested calls to `BeginThreadAffinity` have no effect, because the call refers to the current task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f87b5-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f87b5-126">Requirements</span></span>  
 <span data-ttu-id="f87b5-127">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f87b5-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f87b5-128">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f87b5-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f87b5-129">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="f87b5-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f87b5-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f87b5-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f87b5-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f87b5-131">See also</span></span>
- [<span data-ttu-id="f87b5-132">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="f87b5-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="f87b5-133">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="f87b5-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="f87b5-134">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="f87b5-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="f87b5-135">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="f87b5-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

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
ms.openlocfilehash: 90ae790603f0e41a20993ffef88654211a3168d9
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842361"
---
# <a name="ihosttaskmanagerbeginthreadaffinity-method"></a><span data-ttu-id="bf885-102">Metodo IHostTaskManager::BeginThreadAffinity</span><span class="sxs-lookup"><span data-stu-id="bf885-102">IHostTaskManager::BeginThreadAffinity Method</span></span>
<span data-ttu-id="bf885-103">Notifica all'host che il codice gestito sta immettendo un punto in cui l'attività corrente non deve essere spostata in un altro thread del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="bf885-103">Notifies the host that managed code is entering a period in which the current task must not be moved to another operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf885-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bf885-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="bf885-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bf885-105">Return Value</span></span>  
  
|<span data-ttu-id="bf885-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bf885-106">HRESULT</span></span>|<span data-ttu-id="bf885-107">Description</span><span class="sxs-lookup"><span data-stu-id="bf885-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bf885-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="bf885-108">S_OK</span></span>|<span data-ttu-id="bf885-109">`BeginThreadAffinity`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="bf885-109">`BeginThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="bf885-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bf885-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bf885-111">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="bf885-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bf885-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bf885-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bf885-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="bf885-113">The call timed out.</span></span>|  
|<span data-ttu-id="bf885-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bf885-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bf885-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="bf885-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bf885-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bf885-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bf885-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="bf885-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bf885-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bf885-118">E_FAIL</span></span>|<span data-ttu-id="bf885-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="bf885-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bf885-120">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="bf885-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bf885-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="bf885-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf885-122">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="bf885-122">Remarks</span></span>  
 <span data-ttu-id="bf885-123">CLR chiama in genere `IHostTaskManager::BeginThreadAffinity` nel contesto di una chiamata a <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="bf885-123">The CLR typically calls `IHostTaskManager::BeginThreadAffinity` in the context of a call to <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="bf885-124">L'attività corrente non deve essere ripianificata finché non viene effettuata una chiamata corrispondente a [IHostTaskManager:: EndThreadAffinity](ihosttaskmanager-endthreadaffinity-method.md).</span><span class="sxs-lookup"><span data-stu-id="bf885-124">The current task must not be rescheduled until a corresponding call is made to [IHostTaskManager::EndThreadAffinity](ihosttaskmanager-endthreadaffinity-method.md).</span></span> <span data-ttu-id="bf885-125">Le attività possono essere disattivate, ma quando vengono riattivate, devono essere assegnate allo stesso thread del sistema operativo da cui sono state disattivate. Le chiamate annidate `BeginThreadAffinity` non hanno alcun effetto, perché la chiamata fa riferimento all'attività corrente.</span><span class="sxs-lookup"><span data-stu-id="bf885-125">Tasks can be switched out, but when they are switched back in, they must be assigned to the same operating system thread from which they were switched out. Nested calls to `BeginThreadAffinity` have no effect, because the call refers to the current task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf885-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bf885-126">Requirements</span></span>  
 <span data-ttu-id="bf885-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf885-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf885-128">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="bf885-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bf885-129">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="bf885-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bf885-130">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf885-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf885-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf885-131">See also</span></span>

- [<span data-ttu-id="bf885-132">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="bf885-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="bf885-133">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="bf885-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="bf885-134">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="bf885-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="bf885-135">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="bf885-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)

---
title: Metodo IHostTask::Alert
ms.date: 03/30/2017
api_name:
- IHostTask.Alert
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Alert
helpviewer_keywords:
- IHostTask::Alert method [.NET Framework hosting]
- Alert method, IHostTask interface [.NET Framework hosting]
ms.assetid: 5245d4b5-b6c3-48df-9cb9-8caf059f43fb
topic_type:
- apiref
ms.openlocfilehash: b2fc1d6c45eb72410ccfa1071064aa1a31ae46e6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121409"
---
# <a name="ihosttaskalert-method"></a><span data-ttu-id="5f3ec-102">Metodo IHostTask::Alert</span><span class="sxs-lookup"><span data-stu-id="5f3ec-102">IHostTask::Alert Method</span></span>
<span data-ttu-id="5f3ec-103">Richiede che l'host risvegli l'attività rappresentata dall'istanza corrente di [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) , in modo che l'attività possa essere interrotta.</span><span class="sxs-lookup"><span data-stu-id="5f3ec-103">Requests that the host wake the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance, so the task can be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f3ec-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5f3ec-104">Syntax</span></span>  
  
```cpp  
HRESULT Alert ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5f3ec-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5f3ec-105">Return Value</span></span>  
  
|<span data-ttu-id="5f3ec-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5f3ec-106">HRESULT</span></span>|<span data-ttu-id="5f3ec-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5f3ec-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5f3ec-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="5f3ec-108">S_OK</span></span>|<span data-ttu-id="5f3ec-109">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="5f3ec-109">The method returned successfully.</span></span>|  
|<span data-ttu-id="5f3ec-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5f3ec-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5f3ec-111">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="5f3ec-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5f3ec-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5f3ec-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5f3ec-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="5f3ec-113">The call timed out.</span></span>|  
|<span data-ttu-id="5f3ec-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5f3ec-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5f3ec-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="5f3ec-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5f3ec-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5f3ec-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5f3ec-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="5f3ec-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5f3ec-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5f3ec-118">E_FAIL</span></span>|<span data-ttu-id="5f3ec-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="5f3ec-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5f3ec-120">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="5f3ec-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5f3ec-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5f3ec-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f3ec-122">Note</span><span class="sxs-lookup"><span data-stu-id="5f3ec-122">Remarks</span></span>  
 <span data-ttu-id="5f3ec-123">CLR chiama il metodo `Alert` quando viene chiamato <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> dal codice utente o quando il <xref:System.AppDomain> associato al <xref:System.Threading.Thread> corrente si arresta.</span><span class="sxs-lookup"><span data-stu-id="5f3ec-123">The CLR calls the `Alert` method when <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> is called from user code, or when the <xref:System.AppDomain> associated with the current <xref:System.Threading.Thread> shuts down.</span></span> <span data-ttu-id="5f3ec-124">L'host deve restituire immediatamente, perché la chiamata viene eseguita in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="5f3ec-124">The host must return immediately, because the call is made asynchronously.</span></span> <span data-ttu-id="5f3ec-125">Se l'host non è in grado di avvisare immediatamente l'attività, deve riattivarsi la volta successiva che entra in uno stato in cui può essere avvisato.</span><span class="sxs-lookup"><span data-stu-id="5f3ec-125">If the host cannot alert the task immediately, it must wake up the next time it enters a state in which it can be alerted.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5f3ec-126">`Alert` influiscono solo sulle attività a cui il runtime ha passato un valore [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) di WAIT_ALERTABLE a metodi come [join](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md).</span><span class="sxs-lookup"><span data-stu-id="5f3ec-126">`Alert` affects only those tasks to which the runtime has passed a [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) value of WAIT_ALERTABLE to methods such as [Join](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f3ec-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5f3ec-127">Requirements</span></span>  
 <span data-ttu-id="5f3ec-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f3ec-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f3ec-129">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5f3ec-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5f3ec-130">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5f3ec-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5f3ec-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f3ec-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f3ec-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f3ec-132">See also</span></span>

- [<span data-ttu-id="5f3ec-133">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="5f3ec-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="5f3ec-134">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="5f3ec-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="5f3ec-135">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="5f3ec-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="5f3ec-136">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="5f3ec-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

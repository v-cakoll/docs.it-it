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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c153e6ae8558eeab2efa99765405fb7c84632b01
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110032"
---
# <a name="ihosttaskalert-method"></a><span data-ttu-id="873ff-102">Metodo IHostTask::Alert</span><span class="sxs-lookup"><span data-stu-id="873ff-102">IHostTask::Alert Method</span></span>
<span data-ttu-id="873ff-103">Richiede che l'host di riattivare l'attività rappresentata dall'oggetto corrente [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) dell'istanza, in modo che l'attività può essere interrotta.</span><span class="sxs-lookup"><span data-stu-id="873ff-103">Requests that the host wake the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance, so the task can be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="873ff-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="873ff-104">Syntax</span></span>  
  
```  
HRESULT Alert ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="873ff-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="873ff-105">Return Value</span></span>  
  
|<span data-ttu-id="873ff-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="873ff-106">HRESULT</span></span>|<span data-ttu-id="873ff-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="873ff-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="873ff-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="873ff-108">S_OK</span></span>|<span data-ttu-id="873ff-109">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="873ff-109">The method returned successfully.</span></span>|  
|<span data-ttu-id="873ff-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="873ff-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="873ff-111">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="873ff-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="873ff-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="873ff-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="873ff-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="873ff-113">The call timed out.</span></span>|  
|<span data-ttu-id="873ff-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="873ff-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="873ff-115">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="873ff-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="873ff-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="873ff-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="873ff-117">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="873ff-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="873ff-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="873ff-118">E_FAIL</span></span>|<span data-ttu-id="873ff-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="873ff-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="873ff-120">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="873ff-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="873ff-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="873ff-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="873ff-122">Note</span><span class="sxs-lookup"><span data-stu-id="873ff-122">Remarks</span></span>  
 <span data-ttu-id="873ff-123">CLR chiama il `Alert` metodo quando si <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> viene chiamato dal codice utente, o quando il <xref:System.AppDomain> associato all'oggetto corrente <xref:System.Threading.Thread> arresta.</span><span class="sxs-lookup"><span data-stu-id="873ff-123">The CLR calls the `Alert` method when <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> is called from user code, or when the <xref:System.AppDomain> associated with the current <xref:System.Threading.Thread> shuts down.</span></span> <span data-ttu-id="873ff-124">L'host deve restituire immediatamente, perché la chiamata viene effettuata in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="873ff-124">The host must return immediately, because the call is made asynchronously.</span></span> <span data-ttu-id="873ff-125">Se l'host non è possibile riattivare immediatamente l'attività, è necessario riattivare la volta successiva che entra in uno stato in cui è possibile ricevere un avviso.</span><span class="sxs-lookup"><span data-stu-id="873ff-125">If the host cannot alert the task immediately, it must wake up the next time it enters a state in which it can be alerted.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="873ff-126">`Alert` interessa solo le attività a cui il runtime ha passato una [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valore WAIT_ALERTABLE ai metodi, ad esempio [Join](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md).</span><span class="sxs-lookup"><span data-stu-id="873ff-126">`Alert` affects only those tasks to which the runtime has passed a [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) value of WAIT_ALERTABLE to methods such as [Join](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="873ff-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="873ff-127">Requirements</span></span>  
 <span data-ttu-id="873ff-128">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="873ff-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="873ff-129">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="873ff-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="873ff-130">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="873ff-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="873ff-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="873ff-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="873ff-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="873ff-132">See also</span></span>

- [<span data-ttu-id="873ff-133">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="873ff-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="873ff-134">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="873ff-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="873ff-135">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="873ff-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="873ff-136">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="873ff-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

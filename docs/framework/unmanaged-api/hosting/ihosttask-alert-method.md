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
ms.openlocfilehash: 057e2aafff726b187f36b8b52859b2f2e812e70e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442364"
---
# <a name="ihosttaskalert-method"></a><span data-ttu-id="ec8d3-102">Metodo IHostTask::Alert</span><span class="sxs-lookup"><span data-stu-id="ec8d3-102">IHostTask::Alert Method</span></span>
<span data-ttu-id="ec8d3-103">Richiede che l'host di riattivare l'attività rappresentata dall'oggetto corrente [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) istanza, in modo che l'attività può essere interrotta.</span><span class="sxs-lookup"><span data-stu-id="ec8d3-103">Requests that the host wake the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance, so the task can be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec8d3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ec8d3-104">Syntax</span></span>  
  
```  
HRESULT Alert ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ec8d3-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ec8d3-105">Return Value</span></span>  
  
|<span data-ttu-id="ec8d3-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ec8d3-106">HRESULT</span></span>|<span data-ttu-id="ec8d3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ec8d3-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ec8d3-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="ec8d3-108">S_OK</span></span>|<span data-ttu-id="ec8d3-109">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="ec8d3-109">The method returned successfully.</span></span>|  
|<span data-ttu-id="ec8d3-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ec8d3-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ec8d3-111">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="ec8d3-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ec8d3-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ec8d3-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ec8d3-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="ec8d3-113">The call timed out.</span></span>|  
|<span data-ttu-id="ec8d3-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ec8d3-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ec8d3-115">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="ec8d3-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ec8d3-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ec8d3-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ec8d3-117">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="ec8d3-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ec8d3-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ec8d3-118">E_FAIL</span></span>|<span data-ttu-id="ec8d3-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="ec8d3-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ec8d3-120">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="ec8d3-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ec8d3-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ec8d3-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec8d3-122">Note</span><span class="sxs-lookup"><span data-stu-id="ec8d3-122">Remarks</span></span>  
 <span data-ttu-id="ec8d3-123">CLR chiama il `Alert` metodo quando <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> viene chiamato dal codice utente, o quando il <xref:System.AppDomain> associato all'oggetto corrente <xref:System.Threading.Thread> viene chiuso.</span><span class="sxs-lookup"><span data-stu-id="ec8d3-123">The CLR calls the `Alert` method when <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> is called from user code, or when the <xref:System.AppDomain> associated with the current <xref:System.Threading.Thread> shuts down.</span></span> <span data-ttu-id="ec8d3-124">L'host deve restituire immediatamente, perché la chiamata viene effettuata in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="ec8d3-124">The host must return immediately, because the call is made asynchronously.</span></span> <span data-ttu-id="ec8d3-125">Se l'host non è possibile riattivare immediatamente l'attività, è necessario riattivare la volta successiva che entra in uno stato in cui è possibile ricevere un avviso.</span><span class="sxs-lookup"><span data-stu-id="ec8d3-125">If the host cannot alert the task immediately, it must wake up the next time it enters a state in which it can be alerted.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec8d3-126">`Alert` interessa solo le attività a cui il runtime ha passato un [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valore WAIT_ALERTABLE per i metodi come [Join](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md).</span><span class="sxs-lookup"><span data-stu-id="ec8d3-126">`Alert` affects only those tasks to which the runtime has passed a [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) value of WAIT_ALERTABLE to methods such as [Join](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec8d3-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ec8d3-127">Requirements</span></span>  
 <span data-ttu-id="ec8d3-128">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec8d3-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec8d3-129">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="ec8d3-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ec8d3-130">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="ec8d3-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ec8d3-131">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec8d3-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec8d3-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec8d3-132">See Also</span></span>  
 [<span data-ttu-id="ec8d3-133">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="ec8d3-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="ec8d3-134">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="ec8d3-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="ec8d3-135">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="ec8d3-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="ec8d3-136">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="ec8d3-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

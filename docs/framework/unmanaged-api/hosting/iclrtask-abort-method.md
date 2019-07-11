---
title: Metodo ICLRTask::Abort
ms.date: 03/30/2017
api_name:
- ICLRTask.Abort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::Abort
helpviewer_keywords:
- ICLRTask::Abort method [.NET Framework hosting]
- Abort method, ICLRTask interface [.NET Framework hosting]
ms.assetid: b3594b5f-2e41-4e36-9096-3586276a138c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3e48292d1b0bfaa990cca1b290f769d96938d433
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759024"
---
# <a name="iclrtaskabort-method"></a><span data-ttu-id="470cc-102">Metodo ICLRTask::Abort</span><span class="sxs-lookup"><span data-stu-id="470cc-102">ICLRTask::Abort Method</span></span>
<span data-ttu-id="470cc-103">Richiede che common language runtime (CLR) di interrompere l'attività che l'oggetto corrente [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanza rappresenta.</span><span class="sxs-lookup"><span data-stu-id="470cc-103">Requests that the common language runtime (CLR) abort the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="470cc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="470cc-104">Syntax</span></span>  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="470cc-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="470cc-105">Return Value</span></span>  
  
|<span data-ttu-id="470cc-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="470cc-106">HRESULT</span></span>|<span data-ttu-id="470cc-107">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="470cc-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="470cc-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="470cc-108">S_OK</span></span>|<span data-ttu-id="470cc-109">`Abort` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="470cc-109">`Abort` returned successfully.</span></span>|  
|<span data-ttu-id="470cc-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="470cc-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="470cc-111">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="470cc-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="470cc-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="470cc-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="470cc-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="470cc-113">The call timed out.</span></span>|  
|<span data-ttu-id="470cc-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="470cc-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="470cc-115">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="470cc-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="470cc-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="470cc-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="470cc-117">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="470cc-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="470cc-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="470cc-118">E_FAIL</span></span>|<span data-ttu-id="470cc-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="470cc-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="470cc-120">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="470cc-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="470cc-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="470cc-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="470cc-122">Note</span><span class="sxs-lookup"><span data-stu-id="470cc-122">Remarks</span></span>  
 <span data-ttu-id="470cc-123">Il Common Language Runtime genera una <xref:System.Threading.ThreadAbortException> quando l'host chiama `Abort`.</span><span class="sxs-lookup"><span data-stu-id="470cc-123">The CLR raises a <xref:System.Threading.ThreadAbortException> when the host calls `Abort`.</span></span> <span data-ttu-id="470cc-124">Restituisce immediatamente dopo l'inizializzazione, le informazioni sull'eccezione senza tempi di attesa per il codice utente, ad esempio i finalizzatori o meccanismi di gestione delle eccezioni per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="470cc-124">It returns immediately after the exception information is initialized, without waiting for user code, such as finalizers or exception handling mechanisms, to execute.</span></span> <span data-ttu-id="470cc-125">Le chiamate a `Abort` vengono quindi eseguite rapidamente.</span><span class="sxs-lookup"><span data-stu-id="470cc-125">Calls to `Abort` thus return quickly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="470cc-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="470cc-126">Requirements</span></span>  
 <span data-ttu-id="470cc-127">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="470cc-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="470cc-128">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="470cc-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="470cc-129">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="470cc-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="470cc-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="470cc-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="470cc-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="470cc-131">See also</span></span>

- [<span data-ttu-id="470cc-132">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="470cc-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="470cc-133">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="470cc-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="470cc-134">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="470cc-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="470cc-135">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="470cc-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

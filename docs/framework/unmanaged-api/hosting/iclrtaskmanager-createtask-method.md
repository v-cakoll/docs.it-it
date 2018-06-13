---
title: Metodo ICLRTaskManager::CreateTask
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::CreateTask
helpviewer_keywords:
- ICLRTaskManager::CreateTask method [.NET Framework hosting]
- CreateTask method, ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: eea570d9-2e53-4320-9ea0-eb777bf9dcf3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f731e121324793a027c5977a02e1973b0d6fff20
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439648"
---
# <a name="iclrtaskmanagercreatetask-method"></a><span data-ttu-id="7c229-102">Metodo ICLRTaskManager::CreateTask</span><span class="sxs-lookup"><span data-stu-id="7c229-102">ICLRTaskManager::CreateTask Method</span></span>
<span data-ttu-id="7c229-103">Le richieste in modo esplicito che common language runtime (CLR) creare una nuova attività.</span><span class="sxs-lookup"><span data-stu-id="7c229-103">Requests explicitly that the common language runtime (CLR) create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c229-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7c229-104">Syntax</span></span>  
  
```  
HRESULT CreateTask (  
    [out] ICLRTask **pTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7c229-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7c229-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="7c229-106">[out] Un puntatore all'indirizzo di un oggetto appena creato [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md), o null, se l'attività non è stato creato.</span><span class="sxs-lookup"><span data-stu-id="7c229-106">[out] A pointer to the address of a newly created [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md), or null, if the task could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c229-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7c229-107">Return Value</span></span>  
  
|<span data-ttu-id="7c229-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7c229-108">HRESULT</span></span>|<span data-ttu-id="7c229-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7c229-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7c229-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7c229-110">S_OK</span></span>|<span data-ttu-id="7c229-111">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="7c229-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="7c229-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7c229-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7c229-113">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7c229-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7c229-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7c229-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7c229-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7c229-115">The call timed out.</span></span>|  
|<span data-ttu-id="7c229-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7c229-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7c229-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="7c229-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7c229-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7c229-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7c229-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="7c229-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7c229-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7c229-120">E_FAIL</span></span>|<span data-ttu-id="7c229-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="7c229-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7c229-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="7c229-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7c229-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7c229-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7c229-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="7c229-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="7c229-125">Memoria insufficiente è disponibile per l'allocazione della risorsa richiesta.</span><span class="sxs-lookup"><span data-stu-id="7c229-125">Not enough memory is available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c229-126">Note</span><span class="sxs-lookup"><span data-stu-id="7c229-126">Remarks</span></span>  
 <span data-ttu-id="7c229-127">CLR crea una nuova attività automaticamente al momento dell'inizializzazione, quando il codice utente crea un thread utilizzando tipi di <xref:System.Threading> dello spazio dei nomi, o quando le dimensioni del pool di thread sono aumentata.</span><span class="sxs-lookup"><span data-stu-id="7c229-127">The CLR creates a new task automatically upon initialization, when user code creates a thread by using types in the <xref:System.Threading> namespace, or when the size of the thread pool is increased.</span></span> <span data-ttu-id="7c229-128">Crea inoltre attività quando il codice non gestito effettua una chiamata a una funzione gestita.</span><span class="sxs-lookup"><span data-stu-id="7c229-128">It also creates tasks when unmanaged code makes a call to a managed function.</span></span>  
  
 <span data-ttu-id="7c229-129">`CreateTask` consente all'host effettuare una richiesta esplicita che CLR crea una nuova attività.</span><span class="sxs-lookup"><span data-stu-id="7c229-129">`CreateTask` allows the host to make an explicit request that the CLR create a new task.</span></span> <span data-ttu-id="7c229-130">Ad esempio, l'host è possibile richiamare questo metodo per pre-inizializzare le strutture di dati.</span><span class="sxs-lookup"><span data-stu-id="7c229-130">For example, the host can invoke this method to preinitialize data structures.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7c229-131">La nuova attività, viene restituita in uno stato sospeso e rimane sospesa fino a quando l'host chiama in modo esplicito [IHostTask:: Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="7c229-131">The new task is returned in a suspended state and remains suspended until the host explicitly calls [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c229-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7c229-132">Requirements</span></span>  
 <span data-ttu-id="7c229-133">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c229-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c229-134">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="7c229-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7c229-135">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="7c229-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c229-136">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c229-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c229-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c229-137">See Also</span></span>  
 [<span data-ttu-id="7c229-138">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="7c229-138">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="7c229-139">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="7c229-139">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="7c229-140">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="7c229-140">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="7c229-141">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="7c229-141">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

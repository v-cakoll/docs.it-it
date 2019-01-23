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
ms.openlocfilehash: 3556c9c73d354f096316cf67741a055e9f46adfe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54600274"
---
# <a name="iclrtaskmanagercreatetask-method"></a><span data-ttu-id="6bf34-102">Metodo ICLRTaskManager::CreateTask</span><span class="sxs-lookup"><span data-stu-id="6bf34-102">ICLRTaskManager::CreateTask Method</span></span>
<span data-ttu-id="6bf34-103">Le richieste in modo esplicito che common language runtime (CLR) creare una nuova attività.</span><span class="sxs-lookup"><span data-stu-id="6bf34-103">Requests explicitly that the common language runtime (CLR) create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bf34-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6bf34-104">Syntax</span></span>  
  
```  
HRESULT CreateTask (  
    [out] ICLRTask **pTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6bf34-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6bf34-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="6bf34-106">[out] Un puntatore all'indirizzo di un oggetto appena creato [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md), oppure null se non è stato possibile creare l'attività.</span><span class="sxs-lookup"><span data-stu-id="6bf34-106">[out] A pointer to the address of a newly created [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md), or null, if the task could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6bf34-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6bf34-107">Return Value</span></span>  
  
|<span data-ttu-id="6bf34-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6bf34-108">HRESULT</span></span>|<span data-ttu-id="6bf34-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6bf34-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6bf34-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6bf34-110">S_OK</span></span>|<span data-ttu-id="6bf34-111">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="6bf34-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="6bf34-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6bf34-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6bf34-113">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="6bf34-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6bf34-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6bf34-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6bf34-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="6bf34-115">The call timed out.</span></span>|  
|<span data-ttu-id="6bf34-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6bf34-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6bf34-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="6bf34-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6bf34-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6bf34-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6bf34-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="6bf34-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6bf34-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6bf34-120">E_FAIL</span></span>|<span data-ttu-id="6bf34-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="6bf34-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6bf34-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="6bf34-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6bf34-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6bf34-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6bf34-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="6bf34-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="6bf34-125">Memoria insufficiente è disponibile per allocare la risorsa richiesta.</span><span class="sxs-lookup"><span data-stu-id="6bf34-125">Not enough memory is available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6bf34-126">Note</span><span class="sxs-lookup"><span data-stu-id="6bf34-126">Remarks</span></span>  
 <span data-ttu-id="6bf34-127">CLR crea una nuova attività automaticamente al momento dell'inizializzazione, quando il codice utente crea un thread usando i tipi nel <xref:System.Threading> dello spazio dei nomi, oppure quando sono aumentata le dimensioni del pool di thread.</span><span class="sxs-lookup"><span data-stu-id="6bf34-127">The CLR creates a new task automatically upon initialization, when user code creates a thread by using types in the <xref:System.Threading> namespace, or when the size of the thread pool is increased.</span></span> <span data-ttu-id="6bf34-128">Crea anche le attività quando il codice non gestito effettua una chiamata di una funzione gestita.</span><span class="sxs-lookup"><span data-stu-id="6bf34-128">It also creates tasks when unmanaged code makes a call to a managed function.</span></span>  
  
 <span data-ttu-id="6bf34-129">`CreateTask` consente all'host eseguire una richiesta esplicita che Common Language Runtime crea una nuova attività.</span><span class="sxs-lookup"><span data-stu-id="6bf34-129">`CreateTask` allows the host to make an explicit request that the CLR create a new task.</span></span> <span data-ttu-id="6bf34-130">Ad esempio, l'host può richiamare questo metodo per preinizializzare strutture di dati.</span><span class="sxs-lookup"><span data-stu-id="6bf34-130">For example, the host can invoke this method to preinitialize data structures.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6bf34-131">La nuova attività viene restituita in uno stato sospeso e rimane sospesa fino a quando l'host chiama in modo esplicito [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="6bf34-131">The new task is returned in a suspended state and remains suspended until the host explicitly calls [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bf34-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6bf34-132">Requirements</span></span>  
 <span data-ttu-id="6bf34-133">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6bf34-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bf34-134">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6bf34-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6bf34-135">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="6bf34-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6bf34-136">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bf34-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bf34-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6bf34-137">See also</span></span>
- [<span data-ttu-id="6bf34-138">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="6bf34-138">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="6bf34-139">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="6bf34-139">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="6bf34-140">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="6bf34-140">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="6bf34-141">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="6bf34-141">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

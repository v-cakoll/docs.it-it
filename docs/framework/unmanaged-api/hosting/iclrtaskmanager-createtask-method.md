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
ms.openlocfilehash: 9829f57da911b43626516284e4858adc4139a3ca
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762877"
---
# <a name="iclrtaskmanagercreatetask-method"></a><span data-ttu-id="b8b33-102">Metodo ICLRTaskManager::CreateTask</span><span class="sxs-lookup"><span data-stu-id="b8b33-102">ICLRTaskManager::CreateTask Method</span></span>
<span data-ttu-id="b8b33-103">Richiede in modo esplicito che il Common Language Runtime (CLR) crei una nuova attività.</span><span class="sxs-lookup"><span data-stu-id="b8b33-103">Requests explicitly that the common language runtime (CLR) create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8b33-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b8b33-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateTask (  
    [out] ICLRTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8b33-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b8b33-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="b8b33-106">out Puntatore all'indirizzo di un oggetto [ICLRTask](iclrtask-interface.md)appena creato, o null, se non è stato possibile creare l'attività.</span><span class="sxs-lookup"><span data-stu-id="b8b33-106">[out] A pointer to the address of a newly created [ICLRTask](iclrtask-interface.md), or null, if the task could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b8b33-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b8b33-107">Return Value</span></span>  
  
|<span data-ttu-id="b8b33-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b8b33-108">HRESULT</span></span>|<span data-ttu-id="b8b33-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b8b33-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b8b33-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b8b33-110">S_OK</span></span>|<span data-ttu-id="b8b33-111">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="b8b33-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="b8b33-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b8b33-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b8b33-113">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="b8b33-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b8b33-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b8b33-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b8b33-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b8b33-115">The call timed out.</span></span>|  
|<span data-ttu-id="b8b33-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b8b33-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b8b33-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="b8b33-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b8b33-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b8b33-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b8b33-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="b8b33-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b8b33-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b8b33-120">E_FAIL</span></span>|<span data-ttu-id="b8b33-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="b8b33-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b8b33-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="b8b33-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b8b33-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b8b33-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b8b33-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="b8b33-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="b8b33-125">La memoria disponibile non è sufficiente per allocare la risorsa richiesta.</span><span class="sxs-lookup"><span data-stu-id="b8b33-125">Not enough memory is available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8b33-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b8b33-126">Remarks</span></span>  
 <span data-ttu-id="b8b33-127">CLR crea una nuova attività automaticamente al momento dell'inizializzazione, quando il codice utente crea un thread utilizzando i tipi nello <xref:System.Threading> spazio dei nomi o quando le dimensioni del pool di thread vengono aumentate.</span><span class="sxs-lookup"><span data-stu-id="b8b33-127">The CLR creates a new task automatically upon initialization, when user code creates a thread by using types in the <xref:System.Threading> namespace, or when the size of the thread pool is increased.</span></span> <span data-ttu-id="b8b33-128">Vengono inoltre create attività quando il codice non gestito effettua una chiamata a una funzione gestita.</span><span class="sxs-lookup"><span data-stu-id="b8b33-128">It also creates tasks when unmanaged code makes a call to a managed function.</span></span>  
  
 <span data-ttu-id="b8b33-129">`CreateTask`consente all'host di eseguire una richiesta esplicita che CLR crea una nuova attività.</span><span class="sxs-lookup"><span data-stu-id="b8b33-129">`CreateTask` allows the host to make an explicit request that the CLR create a new task.</span></span> <span data-ttu-id="b8b33-130">Ad esempio, l'host può richiamare questo metodo per preinizializzare le strutture dei dati.</span><span class="sxs-lookup"><span data-stu-id="b8b33-130">For example, the host can invoke this method to preinitialize data structures.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b8b33-131">La nuova attività viene restituita in stato sospeso e rimane sospesa fino a quando l'host non chiama in modo esplicito [IHostTask:: Start](ihosttask-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="b8b33-131">The new task is returned in a suspended state and remains suspended until the host explicitly calls [IHostTask::Start](ihosttask-start-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8b33-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b8b33-132">Requirements</span></span>  
 <span data-ttu-id="b8b33-133">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8b33-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8b33-134">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b8b33-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b8b33-135">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b8b33-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b8b33-136">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8b33-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8b33-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8b33-137">See also</span></span>

- [<span data-ttu-id="b8b33-138">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="b8b33-138">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="b8b33-139">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="b8b33-139">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="b8b33-140">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="b8b33-140">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="b8b33-141">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="b8b33-141">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)

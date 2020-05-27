---
title: Metodo IHostTaskManager::GetCurrentTask
ms.date: 03/30/2017
api_name:
- IHostTaskManager.GetCurrentTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: f17bca49-90bd-4dee-a5e1-b9a57ea46f85
topic_type:
- apiref
ms.openlocfilehash: 874951d6b5efed0dc08e6d0e166962767e295c3e
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842049"
---
# <a name="ihosttaskmanagergetcurrenttask-method"></a><span data-ttu-id="fc319-102">Metodo IHostTaskManager::GetCurrentTask</span><span class="sxs-lookup"><span data-stu-id="fc319-102">IHostTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="fc319-103">Ottiene un puntatore a interfaccia per l'attività attualmente in esecuzione nel thread del sistema operativo da cui viene effettuata la chiamata.</span><span class="sxs-lookup"><span data-stu-id="fc319-103">Gets an interface pointer to the task that is currently executing on the operating system thread from which this call is made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc319-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fc319-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTask (  
    [out] IHostTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc319-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fc319-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="fc319-106">out Puntatore all'indirizzo di un'istanza di [IHostTask](ihosttask-interface.md) che rappresenta l'attività attualmente in esecuzione, o null, se nessuna attività è attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fc319-106">[out] A pointer to the address of an [IHostTask](ihosttask-interface.md) instance that represents the currently executing task, or null, if no task is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fc319-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fc319-107">Return Value</span></span>  
  
|<span data-ttu-id="fc319-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fc319-108">HRESULT</span></span>|<span data-ttu-id="fc319-109">Description</span><span class="sxs-lookup"><span data-stu-id="fc319-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fc319-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="fc319-110">S_OK</span></span>|<span data-ttu-id="fc319-111">`GetCurrentTask`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="fc319-111">`GetCurrentTask` returned successfully.</span></span>|  
|<span data-ttu-id="fc319-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fc319-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fc319-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="fc319-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fc319-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fc319-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fc319-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="fc319-115">The call timed out.</span></span>|  
|<span data-ttu-id="fc319-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fc319-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fc319-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="fc319-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fc319-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fc319-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fc319-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="fc319-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fc319-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fc319-120">E_FAIL</span></span>|<span data-ttu-id="fc319-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="fc319-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fc319-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="fc319-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fc319-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fc319-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fc319-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="fc319-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="fc319-125">`GetCurrentTask`è stato chiamato su un thread del sistema operativo all'esterno del controllo dell'host.</span><span class="sxs-lookup"><span data-stu-id="fc319-125">`GetCurrentTask` was called on an operating system thread outside the control of the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc319-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="fc319-126">Remarks</span></span>  
 <span data-ttu-id="fc319-127">L'host può anche impostare il `pTask` parametro su null per impedire a un'attività che non è stata avviata di accedere a CLR.</span><span class="sxs-lookup"><span data-stu-id="fc319-127">The host can also set the `pTask` parameter to null to prevent a task that it did not initiate from entering the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc319-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fc319-128">Requirements</span></span>  
 <span data-ttu-id="fc319-129">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc319-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc319-130">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fc319-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fc319-131">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fc319-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fc319-132">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc319-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc319-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc319-133">See also</span></span>

- [<span data-ttu-id="fc319-134">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="fc319-134">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="fc319-135">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="fc319-135">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="fc319-136">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="fc319-136">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="fc319-137">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="fc319-137">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)

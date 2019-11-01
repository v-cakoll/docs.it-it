---
title: Metodo ICLRTaskManager::GetCurrentTask
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.GetCurrentTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, ICLRTaskManager interface [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: c0b82a9f-edc6-4878-9c81-48de53c02142
topic_type:
- apiref
ms.openlocfilehash: a57610d1b41d80d54a245b9744aafd78a1e88177
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195900"
---
# <a name="iclrtaskmanagergetcurrenttask-method"></a><span data-ttu-id="ff511-102">Metodo ICLRTaskManager::GetCurrentTask</span><span class="sxs-lookup"><span data-stu-id="ff511-102">ICLRTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="ff511-103">Ottiene l'istanza di [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) attualmente in esecuzione nel thread del sistema operativo da cui ha avuto origine la chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="ff511-103">Gets the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance that is currently running on the operating system thread from which the method call originated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff511-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ff511-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTask (  
    [out] ICLRTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff511-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ff511-105">Parameters</span></span>  
 `ppTask`  
 <span data-ttu-id="ff511-106">out Puntatore all'indirizzo di un'istanza di `ICLRTask` attualmente in esecuzione sul thread del sistema operativo da cui ha avuto origine la chiamata o null se nessuna attività è attualmente in esecuzione su questo thread.</span><span class="sxs-lookup"><span data-stu-id="ff511-106">[out] A pointer to the address of an `ICLRTask` instance that is currently executing on the operating system thread from which the call originated, or null if no task is currently executing on this thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff511-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ff511-107">Return Value</span></span>  
  
|<span data-ttu-id="ff511-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ff511-108">HRESULT</span></span>|<span data-ttu-id="ff511-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ff511-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ff511-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ff511-110">S_OK</span></span>|<span data-ttu-id="ff511-111">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="ff511-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="ff511-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ff511-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ff511-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="ff511-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ff511-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ff511-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ff511-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="ff511-115">The call timed out.</span></span>|  
|<span data-ttu-id="ff511-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ff511-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ff511-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="ff511-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ff511-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ff511-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ff511-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="ff511-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ff511-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ff511-120">E_FAIL</span></span>|<span data-ttu-id="ff511-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="ff511-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ff511-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="ff511-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ff511-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ff511-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff511-124">Note</span><span class="sxs-lookup"><span data-stu-id="ff511-124">Remarks</span></span>  
 <span data-ttu-id="ff511-125">L'istanza di `ICLRTask` a cui punta il parametro di `ppTask` rappresenta l'attività attualmente in esecuzione per CLR.</span><span class="sxs-lookup"><span data-stu-id="ff511-125">The `ICLRTask` instance that the `ppTask` parameter points to represents the currently executing task for the CLR.</span></span> <span data-ttu-id="ff511-126">L'istanza di `ICLRTask` è associata a un'istanza di [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) corrispondente che rappresenta l'attività per l'host.</span><span class="sxs-lookup"><span data-stu-id="ff511-126">The `ICLRTask` instance is associated with a corresponding [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that represents the task for the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff511-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ff511-127">Requirements</span></span>  
 <span data-ttu-id="ff511-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff511-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff511-129">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ff511-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ff511-130">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ff511-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ff511-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff511-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff511-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff511-132">See also</span></span>

- [<span data-ttu-id="ff511-133">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="ff511-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="ff511-134">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="ff511-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="ff511-135">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="ff511-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="ff511-136">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="ff511-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

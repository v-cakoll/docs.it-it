---
title: Metodo IHostTask::Join
ms.date: 03/30/2017
api_name:
- IHostTask.Join
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Join
helpviewer_keywords:
- IHostTask::Join method [.NET Framework hosting]
- Join method, IHostTask interface [.NET Framework hosting]
ms.assetid: 2cffcc52-19e0-4ced-a440-fc7375078ac9
topic_type:
- apiref
ms.openlocfilehash: dda68041dbf4efa82a35c48702d83aa231462fef
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121378"
---
# <a name="ihosttaskjoin-method"></a><span data-ttu-id="50106-102">Metodo IHostTask::Join</span><span class="sxs-lookup"><span data-stu-id="50106-102">IHostTask::Join Method</span></span>
<span data-ttu-id="50106-103">Blocca l'attività chiamante fino a quando l'attività rappresentata dall'istanza corrente di [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) non viene completata, l'intervallo di tempo specificato scade oppure [IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="50106-103">Blocks the calling task until the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance completes, the specified time interval elapses, or [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) is called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50106-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="50106-104">Syntax</span></span>  
  
```cpp  
HRESULT Join (  
    [in] DWORD milliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50106-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="50106-105">Parameters</span></span>  
 `milliseconds`  
 <span data-ttu-id="50106-106">in Intervallo di tempo, in millisecondi, di attesa dell'interruzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="50106-106">[in] The time interval, in milliseconds, to wait for the task to terminate.</span></span> <span data-ttu-id="50106-107">Se questo intervallo scade prima che l'attività venga terminata, l'attività chiamante viene sbloccata.</span><span class="sxs-lookup"><span data-stu-id="50106-107">If this interval elapses before the task terminates, the calling task unblocks.</span></span>  
  
 `option`  
 <span data-ttu-id="50106-108">in Uno dei valori [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="50106-108">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values.</span></span> <span data-ttu-id="50106-109">Il valore WAIT_ALERTABLE indica all'host di riattivare l'attività se `Alert` viene chiamato prima della scadenza di `milliseconds`.</span><span class="sxs-lookup"><span data-stu-id="50106-109">A value of WAIT_ALERTABLE instructs the host to wake the task if `Alert` is called before `milliseconds` elapses.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="50106-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="50106-110">Return Value</span></span>  
  
|<span data-ttu-id="50106-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="50106-111">HRESULT</span></span>|<span data-ttu-id="50106-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="50106-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="50106-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="50106-113">S_OK</span></span>|<span data-ttu-id="50106-114">`Join` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="50106-114">`Join` returned successfully.</span></span>|  
|<span data-ttu-id="50106-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="50106-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="50106-116">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="50106-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="50106-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="50106-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="50106-118">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="50106-118">The call timed out.</span></span>|  
|<span data-ttu-id="50106-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="50106-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="50106-120">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="50106-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="50106-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="50106-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="50106-122">Un evento è stato annullato durante l'attesa di un thread o fiber bloccato oppure l'istanza `IHostTask` corrente non è associata a un'attività.</span><span class="sxs-lookup"><span data-stu-id="50106-122">An event was canceled while a blocked thread or fiber was waiting on it, or the current `IHostTask` instance is not associated with a task.</span></span>|  
|<span data-ttu-id="50106-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="50106-123">E_FAIL</span></span>|<span data-ttu-id="50106-124">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="50106-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="50106-125">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="50106-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="50106-126">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="50106-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="50106-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="50106-127">Requirements</span></span>  
 <span data-ttu-id="50106-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50106-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50106-129">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="50106-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="50106-130">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="50106-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="50106-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50106-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50106-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50106-132">See also</span></span>

- [<span data-ttu-id="50106-133">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="50106-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="50106-134">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="50106-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="50106-135">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="50106-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="50106-136">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="50106-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="50106-137">Enumerazione WAIT_OPTION</span><span class="sxs-lookup"><span data-stu-id="50106-137">WAIT_OPTION Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)

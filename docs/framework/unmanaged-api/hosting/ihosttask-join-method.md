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
ms.openlocfilehash: 20919bd9889408821cf57817082e3c7d5cebc240
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503918"
---
# <a name="ihosttaskjoin-method"></a><span data-ttu-id="6bfcb-102">Metodo IHostTask::Join</span><span class="sxs-lookup"><span data-stu-id="6bfcb-102">IHostTask::Join Method</span></span>
<span data-ttu-id="6bfcb-103">Blocca l'attività chiamante fino a quando l'attività rappresentata dall'istanza corrente di [IHostTask](ihosttask-interface.md) non viene completata, l'intervallo di tempo specificato scade oppure [IHostTask:: Alert](ihosttask-alert-method.md) viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="6bfcb-103">Blocks the calling task until the task represented by the current [IHostTask](ihosttask-interface.md) instance completes, the specified time interval elapses, or [IHostTask::Alert](ihosttask-alert-method.md) is called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bfcb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6bfcb-104">Syntax</span></span>  
  
```cpp  
HRESULT Join (  
    [in] DWORD milliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6bfcb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6bfcb-105">Parameters</span></span>  
 `milliseconds`  
 <span data-ttu-id="6bfcb-106">in Intervallo di tempo, in millisecondi, di attesa dell'interruzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="6bfcb-106">[in] The time interval, in milliseconds, to wait for the task to terminate.</span></span> <span data-ttu-id="6bfcb-107">Se questo intervallo scade prima che l'attività venga terminata, l'attività chiamante viene sbloccata.</span><span class="sxs-lookup"><span data-stu-id="6bfcb-107">If this interval elapses before the task terminates, the calling task unblocks.</span></span>  
  
 `option`  
 <span data-ttu-id="6bfcb-108">in Uno dei valori di [WAIT_OPTION](wait-option-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="6bfcb-108">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values.</span></span> <span data-ttu-id="6bfcb-109">Il valore WAIT_ALERTABLE indica all'host di riattivare l'attività se `Alert` viene chiamato prima della `milliseconds` scadenza.</span><span class="sxs-lookup"><span data-stu-id="6bfcb-109">A value of WAIT_ALERTABLE instructs the host to wake the task if `Alert` is called before `milliseconds` elapses.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6bfcb-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6bfcb-110">Return Value</span></span>  
  
|<span data-ttu-id="6bfcb-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6bfcb-111">HRESULT</span></span>|<span data-ttu-id="6bfcb-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6bfcb-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6bfcb-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="6bfcb-113">S_OK</span></span>|<span data-ttu-id="6bfcb-114">`Join`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="6bfcb-114">`Join` returned successfully.</span></span>|  
|<span data-ttu-id="6bfcb-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6bfcb-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6bfcb-116">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="6bfcb-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6bfcb-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6bfcb-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6bfcb-118">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="6bfcb-118">The call timed out.</span></span>|  
|<span data-ttu-id="6bfcb-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6bfcb-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6bfcb-120">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="6bfcb-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6bfcb-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6bfcb-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6bfcb-122">Un evento è stato annullato durante l'attesa di un thread o fiber bloccato oppure l' `IHostTask` istanza corrente non è associata a un'attività.</span><span class="sxs-lookup"><span data-stu-id="6bfcb-122">An event was canceled while a blocked thread or fiber was waiting on it, or the current `IHostTask` instance is not associated with a task.</span></span>|  
|<span data-ttu-id="6bfcb-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6bfcb-123">E_FAIL</span></span>|<span data-ttu-id="6bfcb-124">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="6bfcb-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6bfcb-125">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="6bfcb-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6bfcb-126">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6bfcb-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6bfcb-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6bfcb-127">Requirements</span></span>  
 <span data-ttu-id="6bfcb-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6bfcb-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bfcb-129">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6bfcb-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6bfcb-130">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6bfcb-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6bfcb-131">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bfcb-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bfcb-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6bfcb-132">See also</span></span>

- [<span data-ttu-id="6bfcb-133">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="6bfcb-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="6bfcb-134">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="6bfcb-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="6bfcb-135">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="6bfcb-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="6bfcb-136">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="6bfcb-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="6bfcb-137">Enumerazione WAIT_OPTION</span><span class="sxs-lookup"><span data-stu-id="6bfcb-137">WAIT_OPTION Enumeration</span></span>](wait-option-enumeration.md)

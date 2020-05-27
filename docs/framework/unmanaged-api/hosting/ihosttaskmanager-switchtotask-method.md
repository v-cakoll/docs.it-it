---
title: Metodo IHostTaskManager::SwitchToTask
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SwitchToTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SwitchToTask
helpviewer_keywords:
- IHostTaskManager::SwitchToTask method [.NET Framework hosting]
- SwitchToTask method [.NET Framework hosting]
ms.assetid: 35d0c27e-4b14-49ce-810d-7ab2120177e8
topic_type:
- apiref
ms.openlocfilehash: 7d1511924fc70c42252881a46f8aebb437a3f4f7
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2020
ms.locfileid: "83841945"
---
# <a name="ihosttaskmanagerswitchtotask-method"></a><span data-ttu-id="22329-102">Metodo IHostTaskManager::SwitchToTask</span><span class="sxs-lookup"><span data-stu-id="22329-102">IHostTaskManager::SwitchToTask Method</span></span>
<span data-ttu-id="22329-103">Notifica all'host che dovrebbe disattivare l'attività corrente.</span><span class="sxs-lookup"><span data-stu-id="22329-103">Notifies the host that it should switch out the current task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22329-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="22329-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchToTask (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22329-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="22329-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="22329-106">in Uno dei valori di enumerazione [WAIT_OPTION](wait-option-enumeration.md) , che indica l'azione che l'host deve eseguire se l'operazione richiesta si blocca.</span><span class="sxs-lookup"><span data-stu-id="22329-106">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) enumeration values, indicating the action the host should take if the requested operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="22329-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="22329-107">Return Value</span></span>  
  
|<span data-ttu-id="22329-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="22329-108">HRESULT</span></span>|<span data-ttu-id="22329-109">Description</span><span class="sxs-lookup"><span data-stu-id="22329-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="22329-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="22329-110">S_OK</span></span>|<span data-ttu-id="22329-111">`SwitchToTask`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="22329-111">`SwitchToTask` returned successfully.</span></span>|  
|<span data-ttu-id="22329-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="22329-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="22329-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="22329-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="22329-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="22329-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="22329-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="22329-115">The call timed out.</span></span>|  
|<span data-ttu-id="22329-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="22329-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="22329-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="22329-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="22329-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="22329-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="22329-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="22329-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="22329-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="22329-120">E_FAIL</span></span>|<span data-ttu-id="22329-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="22329-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="22329-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="22329-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="22329-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="22329-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22329-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="22329-124">Remarks</span></span>  
 <span data-ttu-id="22329-125">L'host può passare a un'altra attività nel modo desiderato o necessario.</span><span class="sxs-lookup"><span data-stu-id="22329-125">The host can switch in another task as desired or needed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="22329-126">`SwitchToTask`non specifica l'attività a cui l'host deve passare; specifica solo l'attività da cui deve passare.</span><span class="sxs-lookup"><span data-stu-id="22329-126">`SwitchToTask` does not specify which task the host should switch to; it specifies only the task that it should switch from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22329-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="22329-127">Requirements</span></span>  
 <span data-ttu-id="22329-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22329-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22329-129">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="22329-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="22329-130">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="22329-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="22329-131">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22329-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22329-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22329-132">See also</span></span>

- [<span data-ttu-id="22329-133">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="22329-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="22329-134">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="22329-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="22329-135">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="22329-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="22329-136">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="22329-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)

---
title: Metodo ICLRTask::ExitTask
ms.date: 03/30/2017
api_name:
- ICLRTask.ExitTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::ExitTask
helpviewer_keywords:
- ExitTask method [.NET Framework hosting]
- ICLRTask::ExitTask method [.NET Framework hosting]
ms.assetid: 746c85a6-4b33-4f72-a2e9-379fdf2e96af
topic_type:
- apiref
ms.openlocfilehash: 3f6ccf2eb25e96e0f94c558fb642b153ae3472c1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124903"
---
# <a name="iclrtaskexittask-method"></a><span data-ttu-id="728f6-102">Metodo ICLRTask::ExitTask</span><span class="sxs-lookup"><span data-stu-id="728f6-102">ICLRTask::ExitTask Method</span></span>
<span data-ttu-id="728f6-103">Notifica al Common Language Runtime (CLR) che l'attività rappresentata dall'istanza corrente di [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) sta per terminare e tenta di arrestare normalmente l'attività.</span><span class="sxs-lookup"><span data-stu-id="728f6-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is ending, and attempts to shut the task down gracefully.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="728f6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="728f6-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="728f6-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="728f6-105">Return Value</span></span>  
  
|<span data-ttu-id="728f6-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="728f6-106">HRESULT</span></span>|<span data-ttu-id="728f6-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="728f6-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="728f6-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="728f6-108">S_OK</span></span>|<span data-ttu-id="728f6-109">`ExitTask` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="728f6-109">`ExitTask` returned successfully.</span></span>|  
|<span data-ttu-id="728f6-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="728f6-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="728f6-111">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="728f6-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="728f6-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="728f6-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="728f6-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="728f6-113">The call timed out.</span></span>|  
|<span data-ttu-id="728f6-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="728f6-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="728f6-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="728f6-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="728f6-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="728f6-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="728f6-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="728f6-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="728f6-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="728f6-118">E_FAIL</span></span>|<span data-ttu-id="728f6-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="728f6-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="728f6-120">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="728f6-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="728f6-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="728f6-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="728f6-122">Note</span><span class="sxs-lookup"><span data-stu-id="728f6-122">Remarks</span></span>  
 <span data-ttu-id="728f6-123">`ExitTask` tenta un arresto normale di un'attività, in modo analogo allo scollegamento di un thread da una libreria dei tipi non gestita.</span><span class="sxs-lookup"><span data-stu-id="728f6-123">`ExitTask` attempts a clean shutdown of a task, in a manner analogous to detaching a thread from an unmanaged type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="728f6-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="728f6-124">Requirements</span></span>  
 <span data-ttu-id="728f6-125">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="728f6-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="728f6-126">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="728f6-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="728f6-127">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="728f6-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="728f6-128">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="728f6-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="728f6-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="728f6-129">See also</span></span>

- [<span data-ttu-id="728f6-130">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="728f6-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="728f6-131">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="728f6-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="728f6-132">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="728f6-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="728f6-133">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="728f6-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

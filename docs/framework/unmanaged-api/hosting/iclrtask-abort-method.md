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
ms.openlocfilehash: 76f216b12bccc950a34e2b23404ac305de519f4a
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762474"
---
# <a name="iclrtaskabort-method"></a><span data-ttu-id="f3b28-102">Metodo ICLRTask::Abort</span><span class="sxs-lookup"><span data-stu-id="f3b28-102">ICLRTask::Abort Method</span></span>
<span data-ttu-id="f3b28-103">Richiede che il Common Language Runtime (CLR) interrompa l'attività rappresentata dall'istanza corrente di [ICLRTask](iclrtask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="f3b28-103">Requests that the common language runtime (CLR) abort the task that the current [ICLRTask](iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3b28-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f3b28-104">Syntax</span></span>  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f3b28-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f3b28-105">Return Value</span></span>  
  
|<span data-ttu-id="f3b28-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f3b28-106">HRESULT</span></span>|<span data-ttu-id="f3b28-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f3b28-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f3b28-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="f3b28-108">S_OK</span></span>|<span data-ttu-id="f3b28-109">`Abort`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="f3b28-109">`Abort` returned successfully.</span></span>|  
|<span data-ttu-id="f3b28-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f3b28-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f3b28-111">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="f3b28-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f3b28-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f3b28-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f3b28-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f3b28-113">The call timed out.</span></span>|  
|<span data-ttu-id="f3b28-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f3b28-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f3b28-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="f3b28-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f3b28-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f3b28-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f3b28-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="f3b28-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f3b28-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f3b28-118">E_FAIL</span></span>|<span data-ttu-id="f3b28-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="f3b28-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f3b28-120">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="f3b28-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f3b28-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f3b28-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3b28-122">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f3b28-122">Remarks</span></span>  
 <span data-ttu-id="f3b28-123">CLR genera un oggetto <xref:System.Threading.ThreadAbortException> quando l'host chiama `Abort` .</span><span class="sxs-lookup"><span data-stu-id="f3b28-123">The CLR raises a <xref:System.Threading.ThreadAbortException> when the host calls `Abort`.</span></span> <span data-ttu-id="f3b28-124">Viene restituito immediatamente dopo l'inizializzazione delle informazioni sull'eccezione, senza attendere l'esecuzione del codice utente, ad esempio finalizzatori o meccanismi di gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="f3b28-124">It returns immediately after the exception information is initialized, without waiting for user code, such as finalizers or exception handling mechanisms, to execute.</span></span> <span data-ttu-id="f3b28-125">Le chiamate a `Abort` restituiscono quindi rapidamente.</span><span class="sxs-lookup"><span data-stu-id="f3b28-125">Calls to `Abort` thus return quickly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3b28-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f3b28-126">Requirements</span></span>  
 <span data-ttu-id="f3b28-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3b28-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3b28-128">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f3b28-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f3b28-129">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f3b28-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f3b28-130">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3b28-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3b28-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3b28-131">See also</span></span>

- [<span data-ttu-id="f3b28-132">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="f3b28-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="f3b28-133">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="f3b28-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="f3b28-134">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="f3b28-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="f3b28-135">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="f3b28-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)

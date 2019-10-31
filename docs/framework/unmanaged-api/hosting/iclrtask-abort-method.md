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
ms.openlocfilehash: 026d4c14abed030b80e8e1b3f8363fbd59ac05e4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124910"
---
# <a name="iclrtaskabort-method"></a><span data-ttu-id="2b319-102">Metodo ICLRTask::Abort</span><span class="sxs-lookup"><span data-stu-id="2b319-102">ICLRTask::Abort Method</span></span>
<span data-ttu-id="2b319-103">Richiede che il Common Language Runtime (CLR) interrompa l'attività rappresentata dall'istanza corrente di [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="2b319-103">Requests that the common language runtime (CLR) abort the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b319-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2b319-104">Syntax</span></span>  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="2b319-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2b319-105">Return Value</span></span>  
  
|<span data-ttu-id="2b319-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2b319-106">HRESULT</span></span>|<span data-ttu-id="2b319-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b319-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2b319-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="2b319-108">S_OK</span></span>|<span data-ttu-id="2b319-109">`Abort` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2b319-109">`Abort` returned successfully.</span></span>|  
|<span data-ttu-id="2b319-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2b319-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2b319-111">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="2b319-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2b319-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2b319-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2b319-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="2b319-113">The call timed out.</span></span>|  
|<span data-ttu-id="2b319-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2b319-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2b319-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="2b319-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2b319-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2b319-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2b319-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="2b319-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2b319-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2b319-118">E_FAIL</span></span>|<span data-ttu-id="2b319-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="2b319-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2b319-120">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="2b319-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2b319-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2b319-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b319-122">Note</span><span class="sxs-lookup"><span data-stu-id="2b319-122">Remarks</span></span>  
 <span data-ttu-id="2b319-123">CLR genera un'<xref:System.Threading.ThreadAbortException> quando l'host chiama `Abort`.</span><span class="sxs-lookup"><span data-stu-id="2b319-123">The CLR raises a <xref:System.Threading.ThreadAbortException> when the host calls `Abort`.</span></span> <span data-ttu-id="2b319-124">Viene restituito immediatamente dopo l'inizializzazione delle informazioni sull'eccezione, senza attendere l'esecuzione del codice utente, ad esempio finalizzatori o meccanismi di gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="2b319-124">It returns immediately after the exception information is initialized, without waiting for user code, such as finalizers or exception handling mechanisms, to execute.</span></span> <span data-ttu-id="2b319-125">Le chiamate a `Abort` quindi restituiscono rapidamente.</span><span class="sxs-lookup"><span data-stu-id="2b319-125">Calls to `Abort` thus return quickly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b319-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2b319-126">Requirements</span></span>  
 <span data-ttu-id="2b319-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b319-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b319-128">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2b319-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2b319-129">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2b319-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2b319-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b319-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b319-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b319-131">See also</span></span>

- [<span data-ttu-id="2b319-132">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="2b319-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="2b319-133">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="2b319-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="2b319-134">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="2b319-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="2b319-135">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="2b319-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

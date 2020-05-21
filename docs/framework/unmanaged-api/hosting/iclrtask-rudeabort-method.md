---
title: Metodo ICLRTask::RudeAbort
ms.date: 03/30/2017
api_name:
- ICLRTask.RudeAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::RudeAbort
helpviewer_keywords:
- RudeAbort method, ICLRTask interface [.NET Framework hosting]
- ICLRTask::RudeAbort method [.NET Framework hosting]
ms.assetid: b5785468-fcd7-4cc3-8a5d-8796337b53fc
topic_type:
- apiref
ms.openlocfilehash: 5d6e19fe307373c2920fd60b04bff482b238c5c4
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762955"
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="c1ad9-102">Metodo ICLRTask::RudeAbort</span><span class="sxs-lookup"><span data-stu-id="c1ad9-102">ICLRTask::RudeAbort Method</span></span>
<span data-ttu-id="c1ad9-103">Indica al Common Language Runtime (CLR) di interrompere immediatamente l'attività rappresentata dall'istanza dell' [interfaccia ICLRTask](iclrtask-interface.md) corrente e in modo non condizionale.</span><span class="sxs-lookup"><span data-stu-id="c1ad9-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1ad9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c1ad9-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();
```  
  
## <a name="return-value"></a><span data-ttu-id="c1ad9-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c1ad9-105">Return Value</span></span>  
  
|<span data-ttu-id="c1ad9-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c1ad9-106">HRESULT</span></span>|<span data-ttu-id="c1ad9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c1ad9-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c1ad9-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="c1ad9-108">S_OK</span></span>|<span data-ttu-id="c1ad9-109">`RudeAbort`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="c1ad9-109">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="c1ad9-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c1ad9-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c1ad9-111">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="c1ad9-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c1ad9-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c1ad9-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c1ad9-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="c1ad9-113">The call timed out.</span></span>|  
|<span data-ttu-id="c1ad9-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c1ad9-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c1ad9-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="c1ad9-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c1ad9-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c1ad9-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c1ad9-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="c1ad9-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c1ad9-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c1ad9-118">E_FAIL</span></span>|<span data-ttu-id="c1ad9-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="c1ad9-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c1ad9-120">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="c1ad9-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c1ad9-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c1ad9-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1ad9-122">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c1ad9-122">Remarks</span></span>  
 <span data-ttu-id="c1ad9-123">Un host chiama `RudeAbort` per interrompere immediatamente un'attività.</span><span class="sxs-lookup"><span data-stu-id="c1ad9-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="c1ad9-124">Non è garantito l'esecuzione di finalizzatori e routine di gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="c1ad9-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1ad9-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c1ad9-125">Requirements</span></span>  
 <span data-ttu-id="c1ad9-126">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1ad9-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1ad9-127">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c1ad9-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c1ad9-128">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c1ad9-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c1ad9-129">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1ad9-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1ad9-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1ad9-130">See also</span></span>

- [<span data-ttu-id="c1ad9-131">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="c1ad9-131">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="c1ad9-132">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="c1ad9-132">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="c1ad9-133">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="c1ad9-133">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="c1ad9-134">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="c1ad9-134">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)

---
title: Metodo ICLRTask::SetTaskIdentifier
ms.date: 03/30/2017
api_name:
- ICLRTask.SetTaskIdentifier
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SetTaskIdentifier
helpviewer_keywords:
- SetTaskIdentifier method [.NET Framework hosting]
- ICLRTask::SetTaskIdentifier method [.NET Framework hosting]
ms.assetid: bdb7f047-1e90-40fc-9e3b-d44a16509073
topic_type:
- apiref
ms.openlocfilehash: e1b93356fd40aacdec2e764946e3e3b12d0bd306
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762942"
---
# <a name="iclrtasksettaskidentifier-method"></a><span data-ttu-id="76636-102">Metodo ICLRTask::SetTaskIdentifier</span><span class="sxs-lookup"><span data-stu-id="76636-102">ICLRTask::SetTaskIdentifier Method</span></span>
<span data-ttu-id="76636-103">Indica al Common Language Runtime (CLR) di associare il valore dell'identificatore specificato all'attività rappresentata dall'istanza di [ICLRTask](iclrtask-interface.md) corrente.</span><span class="sxs-lookup"><span data-stu-id="76636-103">Instructs the common language runtime (CLR) to associate the specified identifier value with the task represented by the current [ICLRTask](iclrtask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76636-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="76636-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTaskIdentifier (  
    [in] DWORD Asked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76636-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="76636-105">Parameters</span></span>  
 `Asked`  
 <span data-ttu-id="76636-106">in Identificatore univoco per la Common Language Runtime da associare all'attività rappresentata dall' `ICLRTask` istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="76636-106">[in] The unique identifier for the common language runtime to associate with the task represented by the current `ICLRTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="76636-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="76636-107">Return Value</span></span>  
  
|<span data-ttu-id="76636-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="76636-108">HRESULT</span></span>|<span data-ttu-id="76636-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="76636-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="76636-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="76636-110">S_OK</span></span>|<span data-ttu-id="76636-111">`SetTaskIdentifier`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="76636-111">`SetTaskIdentifier` returned successfully.</span></span>|  
|<span data-ttu-id="76636-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="76636-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="76636-113">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="76636-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="76636-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="76636-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="76636-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="76636-115">The call timed out.</span></span>|  
|<span data-ttu-id="76636-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="76636-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="76636-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="76636-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="76636-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="76636-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="76636-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="76636-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="76636-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="76636-120">E_FAIL</span></span>|<span data-ttu-id="76636-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="76636-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="76636-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="76636-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="76636-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="76636-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76636-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="76636-124">Remarks</span></span>  
 <span data-ttu-id="76636-125">L'host può associare un identificatore a un'attività che consente di integrare CLR e l'host in un ambiente di debug.</span><span class="sxs-lookup"><span data-stu-id="76636-125">The host can associate an identifier with a task to help integrate the CLR and the host in a debugging environment.</span></span> <span data-ttu-id="76636-126">L'identificatore non ha significato per CLR.</span><span class="sxs-lookup"><span data-stu-id="76636-126">The identifier has no meaning for the CLR.</span></span> <span data-ttu-id="76636-127">CLR lo passa a un'applicazione del debugger.</span><span class="sxs-lookup"><span data-stu-id="76636-127">The CLR passes it along to a debugger application.</span></span> <span data-ttu-id="76636-128">Il debugger può utilizzare questo identificatore per associare uno stack di chiamate CLR a uno stack di chiamate host e consentire la unificazione delle rispettive informazioni di traccia quando vengono visualizzate nell'interfaccia utente del debugger.</span><span class="sxs-lookup"><span data-stu-id="76636-128">The debugger can use this identifier to associate a CLR call stack with a host call stack, and enable their respective trace information to be unified when viewed in the debugger's user interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76636-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="76636-129">Requirements</span></span>  
 <span data-ttu-id="76636-130">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76636-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76636-131">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="76636-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="76636-132">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="76636-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="76636-133">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76636-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76636-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76636-134">See also</span></span>

- [<span data-ttu-id="76636-135">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="76636-135">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="76636-136">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="76636-136">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="76636-137">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="76636-137">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="76636-138">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="76636-138">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)

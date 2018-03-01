---
title: Metodo IHostThreadPoolManager::QueueUserWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostThreadPoolManager.QueueUserWorkItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::QueueUserWorkItem
helpviewer_keywords:
- IHostThreadPoolManager::QueueUserWorkItem method [.NET Framework hosting]
- QueueUserWorkItem method [.NET Framework hosting]
ms.assetid: 41602053-8670-4827-9d61-cbfcba509b9c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c0a304c2052192d3cba761a128e15dc463011030
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ihostthreadpoolmanagerqueueuserworkitem-method"></a><span data-ttu-id="93073-102">Metodo IHostThreadPoolManager::QueueUserWorkItem</span><span class="sxs-lookup"><span data-stu-id="93073-102">IHostThreadPoolManager::QueueUserWorkItem Method</span></span>
<span data-ttu-id="93073-103">Accoda una funzione per l'esecuzione e specifica un oggetto contenente dati da utilizzare per tale funzione.</span><span class="sxs-lookup"><span data-stu-id="93073-103">Queues a function for execution, and specifies an object containing data to be used by that function.</span></span> <span data-ttu-id="93073-104">La funzione viene eseguita quando un thread diventa disponibile.</span><span class="sxs-lookup"><span data-stu-id="93073-104">The function executes when a thread becomes available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93073-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="93073-105">Syntax</span></span>  
  
```  
HRESULT QueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID Context,  
    [in] ULONG Flags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="93073-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="93073-106">Parameters</span></span>  
 `Function`  
 <span data-ttu-id="93073-107">[in] Un puntatore a funzione che rappresenta la funzione da eseguire.</span><span class="sxs-lookup"><span data-stu-id="93073-107">[in] A function pointer that represents the function to execute.</span></span>  
  
 `Context`  
 <span data-ttu-id="93073-108">[in] Oggetto che contiene i dati da utilizzare da `Function`.</span><span class="sxs-lookup"><span data-stu-id="93073-108">[in] An object that contains data to be used by `Function`.</span></span>  
  
 `Flags`  
 <span data-ttu-id="93073-109">[in] Uno dei flag di valori, come definito per Win32 `QueueUserWorkItem` (metodo), che controlla l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="93073-109">[in] One of the flags values, as defined for the Win32 `QueueUserWorkItem` method, that control execution.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="93073-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="93073-110">Return Value</span></span>  
  
|<span data-ttu-id="93073-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="93073-111">HRESULT</span></span>|<span data-ttu-id="93073-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="93073-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="93073-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="93073-113">S_OK</span></span>|<span data-ttu-id="93073-114">`QueueUserWorkItem`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="93073-114">`QueueUserWorkItem` returned successfully.</span></span>|  
|<span data-ttu-id="93073-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="93073-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="93073-116">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="93073-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="93073-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="93073-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="93073-118">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="93073-118">The call timed out.</span></span>|  
|<span data-ttu-id="93073-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="93073-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="93073-120">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="93073-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="93073-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="93073-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="93073-122">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="93073-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="93073-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="93073-123">E_FAIL</span></span>|<span data-ttu-id="93073-124">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="93073-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="93073-125">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="93073-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="93073-126">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="93073-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93073-127">Note</span><span class="sxs-lookup"><span data-stu-id="93073-127">Remarks</span></span>  
 <span data-ttu-id="93073-128">`QueueUserWorkItem`Accoda un elemento di lavoro a un thread di lavoro nel pool di thread.</span><span class="sxs-lookup"><span data-stu-id="93073-128">`QueueUserWorkItem` queues a work item to a worker thread in the thread pool.</span></span> <span data-ttu-id="93073-129">La firma e tipi di parametro sono identiche a quelle della funzione Win32 corrispondente, che ha lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="93073-129">Its signature and parameter types are identical to those of the corresponding Win32 function, which has the same name.</span></span> <span data-ttu-id="93073-130">Per ulteriori informazioni, vedere la documentazione di piattaforma di Windows.</span><span class="sxs-lookup"><span data-stu-id="93073-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93073-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="93073-131">Requirements</span></span>  
 <span data-ttu-id="93073-132">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93073-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93073-133">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="93073-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="93073-134">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="93073-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="93073-135">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93073-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93073-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93073-136">See Also</span></span>  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="93073-137">Interfaccia IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="93073-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)

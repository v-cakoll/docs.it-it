---
title: Metodo IHostThreadPoolManager::QueueUserWorkItem
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1c548ae7f8d605ff84da2046d057e436c8e95721
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796572"
---
# <a name="ihostthreadpoolmanagerqueueuserworkitem-method"></a><span data-ttu-id="9e36c-102">Metodo IHostThreadPoolManager::QueueUserWorkItem</span><span class="sxs-lookup"><span data-stu-id="9e36c-102">IHostThreadPoolManager::QueueUserWorkItem Method</span></span>
<span data-ttu-id="9e36c-103">Accoda una funzione per l'esecuzione e specifica un oggetto contenente dati da utilizzare da tale funzione.</span><span class="sxs-lookup"><span data-stu-id="9e36c-103">Queues a function for execution, and specifies an object containing data to be used by that function.</span></span> <span data-ttu-id="9e36c-104">La funzione viene eseguita quando un thread diventa disponibile.</span><span class="sxs-lookup"><span data-stu-id="9e36c-104">The function executes when a thread becomes available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e36c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9e36c-105">Syntax</span></span>  
  
```  
HRESULT QueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID Context,  
    [in] ULONG Flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e36c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="9e36c-106">Parameters</span></span>  
 `Function`  
 <span data-ttu-id="9e36c-107">[in] Un puntatore a funzione che rappresenta la funzione da eseguire.</span><span class="sxs-lookup"><span data-stu-id="9e36c-107">[in] A function pointer that represents the function to execute.</span></span>  
  
 `Context`  
 <span data-ttu-id="9e36c-108">[in] Oggetto che contiene dati utilizzabili da `Function`.</span><span class="sxs-lookup"><span data-stu-id="9e36c-108">[in] An object that contains data to be used by `Function`.</span></span>  
  
 `Flags`  
 <span data-ttu-id="9e36c-109">[in] Uno dei flag di valori, come definito per Win32 `QueueUserWorkItem` (metodo), che consentono di controllare l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9e36c-109">[in] One of the flags values, as defined for the Win32 `QueueUserWorkItem` method, that control execution.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9e36c-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9e36c-110">Return Value</span></span>  
  
|<span data-ttu-id="9e36c-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9e36c-111">HRESULT</span></span>|<span data-ttu-id="9e36c-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e36c-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9e36c-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="9e36c-113">S_OK</span></span>|<span data-ttu-id="9e36c-114">`QueueUserWorkItem` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="9e36c-114">`QueueUserWorkItem` returned successfully.</span></span>|  
|<span data-ttu-id="9e36c-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9e36c-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9e36c-116">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9e36c-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9e36c-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9e36c-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9e36c-118">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9e36c-118">The call timed out.</span></span>|  
|<span data-ttu-id="9e36c-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9e36c-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9e36c-120">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="9e36c-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9e36c-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9e36c-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9e36c-122">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="9e36c-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9e36c-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9e36c-123">E_FAIL</span></span>|<span data-ttu-id="9e36c-124">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="9e36c-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9e36c-125">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="9e36c-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9e36c-126">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9e36c-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e36c-127">Note</span><span class="sxs-lookup"><span data-stu-id="9e36c-127">Remarks</span></span>  
 <span data-ttu-id="9e36c-128">`QueueUserWorkItem` Accoda un elemento di lavoro a un thread di lavoro nel pool di thread.</span><span class="sxs-lookup"><span data-stu-id="9e36c-128">`QueueUserWorkItem` queues a work item to a worker thread in the thread pool.</span></span> <span data-ttu-id="9e36c-129">La firma e tipi di parametro sono identiche a quelle della funzione Win32 corrispondente, che ha lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="9e36c-129">Its signature and parameter types are identical to those of the corresponding Win32 function, which has the same name.</span></span> <span data-ttu-id="9e36c-130">Per altre informazioni, vedere la documentazione della piattaforma Windows.</span><span class="sxs-lookup"><span data-stu-id="9e36c-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e36c-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9e36c-131">Requirements</span></span>  
 <span data-ttu-id="9e36c-132">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e36c-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e36c-133">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9e36c-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9e36c-134">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="9e36c-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9e36c-135">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e36c-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e36c-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e36c-136">See also</span></span>

- <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="9e36c-137">Interfaccia IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="9e36c-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)

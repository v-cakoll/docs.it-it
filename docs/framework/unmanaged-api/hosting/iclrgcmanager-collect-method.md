---
title: Metodo ICLRGCManager::Collect
ms.date: 03/30/2017
api_name:
- ICLRGCManager.Collect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::Collect
helpviewer_keywords:
- ICLRGCManager::Collect method [.NET Framework hosting]
- Collect method, ICLRGCManager interface [.NET Framework hosting]
ms.assetid: 0c6cbbea-c27c-4695-bda3-17c1910d8ddb
topic_type:
- apiref
ms.openlocfilehash: aa906e314c408b7653e611b07d7ad21d4519b715
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616983"
---
# <a name="iclrgcmanagercollect-method"></a><span data-ttu-id="5ee42-102">Metodo ICLRGCManager::Collect</span><span class="sxs-lookup"><span data-stu-id="5ee42-102">ICLRGCManager::Collect Method</span></span>
<span data-ttu-id="5ee42-103">Impone un Garbage Collection per la generazione specificata.</span><span class="sxs-lookup"><span data-stu-id="5ee42-103">Forces a garbage collection for the specified generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ee42-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5ee42-104">Syntax</span></span>  
  
```cpp  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ee42-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5ee42-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="5ee42-106">in Generazione da raccogliere.</span><span class="sxs-lookup"><span data-stu-id="5ee42-106">[in] The generation to collect.</span></span> <span data-ttu-id="5ee42-107">Il valore-1 impone una raccolta di tutte le generazioni.</span><span class="sxs-lookup"><span data-stu-id="5ee42-107">A value of -1 forces a collection of all generations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5ee42-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5ee42-108">Return Value</span></span>  
  
|<span data-ttu-id="5ee42-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5ee42-109">HRESULT</span></span>|<span data-ttu-id="5ee42-110">Description</span><span class="sxs-lookup"><span data-stu-id="5ee42-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5ee42-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5ee42-111">S_OK</span></span>|<span data-ttu-id="5ee42-112">`Collect`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="5ee42-112">`Collect` returned successfully.</span></span>|  
|<span data-ttu-id="5ee42-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5ee42-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5ee42-114">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="5ee42-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5ee42-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5ee42-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5ee42-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="5ee42-116">The call timed out.</span></span>|  
|<span data-ttu-id="5ee42-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5ee42-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5ee42-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="5ee42-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5ee42-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5ee42-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5ee42-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="5ee42-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5ee42-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5ee42-121">E_FAIL</span></span>|<span data-ttu-id="5ee42-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="5ee42-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5ee42-123">Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="5ee42-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5ee42-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5ee42-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ee42-125">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5ee42-125">Remarks</span></span>  
 <span data-ttu-id="5ee42-126">Il `Collect` metodo impone all'Garbage Collector di CLR di eseguire una raccolta indipendentemente dallo stato corrente.</span><span class="sxs-lookup"><span data-stu-id="5ee42-126">The `Collect` method forces the CLR's garbage collector to perform a collection regardless of its current state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ee42-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5ee42-127">Requirements</span></span>  
 <span data-ttu-id="5ee42-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ee42-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ee42-129">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5ee42-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5ee42-130">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5ee42-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5ee42-131">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ee42-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ee42-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ee42-132">See also</span></span>

- [<span data-ttu-id="5ee42-133">Gestione automatica della memoria</span><span class="sxs-lookup"><span data-stu-id="5ee42-133">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="5ee42-134">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="5ee42-134">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="5ee42-135">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="5ee42-135">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="5ee42-136">Interfaccia ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="5ee42-136">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)
- [<span data-ttu-id="5ee42-137">Interfacce di hosting CLR</span><span class="sxs-lookup"><span data-stu-id="5ee42-137">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="5ee42-138">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="5ee42-138">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="5ee42-139">Hosting</span><span class="sxs-lookup"><span data-stu-id="5ee42-139">Hosting</span></span>](index.md)

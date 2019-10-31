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
ms.openlocfilehash: a7dae98d1f2dc2448bd3a5df2d6143b7be0bb734
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129268"
---
# <a name="iclrgcmanagercollect-method"></a><span data-ttu-id="b16c6-102">Metodo ICLRGCManager::Collect</span><span class="sxs-lookup"><span data-stu-id="b16c6-102">ICLRGCManager::Collect Method</span></span>
<span data-ttu-id="b16c6-103">Impone un Garbage Collection per la generazione specificata.</span><span class="sxs-lookup"><span data-stu-id="b16c6-103">Forces a garbage collection for the specified generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b16c6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b16c6-104">Syntax</span></span>  
  
```cpp  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b16c6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b16c6-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="b16c6-106">in Generazione da raccogliere.</span><span class="sxs-lookup"><span data-stu-id="b16c6-106">[in] The generation to collect.</span></span> <span data-ttu-id="b16c6-107">Il valore-1 impone una raccolta di tutte le generazioni.</span><span class="sxs-lookup"><span data-stu-id="b16c6-107">A value of -1 forces a collection of all generations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b16c6-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b16c6-108">Return Value</span></span>  
  
|<span data-ttu-id="b16c6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b16c6-109">HRESULT</span></span>|<span data-ttu-id="b16c6-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b16c6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b16c6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b16c6-111">S_OK</span></span>|<span data-ttu-id="b16c6-112">`Collect` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="b16c6-112">`Collect` returned successfully.</span></span>|  
|<span data-ttu-id="b16c6-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b16c6-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b16c6-114">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="b16c6-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b16c6-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b16c6-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b16c6-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b16c6-116">The call timed out.</span></span>|  
|<span data-ttu-id="b16c6-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b16c6-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b16c6-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="b16c6-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b16c6-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b16c6-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b16c6-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="b16c6-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b16c6-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b16c6-121">E_FAIL</span></span>|<span data-ttu-id="b16c6-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="b16c6-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b16c6-123">Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="b16c6-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b16c6-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b16c6-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b16c6-125">Note</span><span class="sxs-lookup"><span data-stu-id="b16c6-125">Remarks</span></span>  
 <span data-ttu-id="b16c6-126">Il metodo `Collect` impone al Garbage Collector di CLR di eseguire una raccolta indipendentemente dallo stato corrente.</span><span class="sxs-lookup"><span data-stu-id="b16c6-126">The `Collect` method forces the CLR's garbage collector to perform a collection regardless of its current state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b16c6-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b16c6-127">Requirements</span></span>  
 <span data-ttu-id="b16c6-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b16c6-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b16c6-129">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b16c6-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b16c6-130">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b16c6-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b16c6-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b16c6-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b16c6-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b16c6-132">See also</span></span>

- [<span data-ttu-id="b16c6-133">Gestione automatica della memoria</span><span class="sxs-lookup"><span data-stu-id="b16c6-133">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="b16c6-134">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="b16c6-134">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="b16c6-135">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="b16c6-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="b16c6-136">Interfaccia ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="b16c6-136">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="b16c6-137">Interfacce di hosting CLR</span><span class="sxs-lookup"><span data-stu-id="b16c6-137">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="b16c6-138">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="b16c6-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="b16c6-139">Hosting</span><span class="sxs-lookup"><span data-stu-id="b16c6-139">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)

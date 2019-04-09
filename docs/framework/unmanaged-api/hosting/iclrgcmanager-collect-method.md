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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1746527a2667676dfeab89e72874204460bcd33c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59126672"
---
# <a name="iclrgcmanagercollect-method"></a><span data-ttu-id="5b341-102">Metodo ICLRGCManager::Collect</span><span class="sxs-lookup"><span data-stu-id="5b341-102">ICLRGCManager::Collect Method</span></span>
<span data-ttu-id="5b341-103">Forza un'operazione di garbage collection per la generazione specificata.</span><span class="sxs-lookup"><span data-stu-id="5b341-103">Forces a garbage collection for the specified generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b341-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5b341-104">Syntax</span></span>  
  
```  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b341-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5b341-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="5b341-106">[in] La generazione da raccogliere.</span><span class="sxs-lookup"><span data-stu-id="5b341-106">[in] The generation to collect.</span></span> <span data-ttu-id="5b341-107">Il valore -1 forza una raccolta di tutte le generazioni.</span><span class="sxs-lookup"><span data-stu-id="5b341-107">A value of -1 forces a collection of all generations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5b341-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5b341-108">Return Value</span></span>  
  
|<span data-ttu-id="5b341-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5b341-109">HRESULT</span></span>|<span data-ttu-id="5b341-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5b341-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5b341-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5b341-111">S_OK</span></span>|`Collect` <span data-ttu-id="5b341-112">stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="5b341-112">returned successfully.</span></span>|  
|<span data-ttu-id="5b341-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5b341-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5b341-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="5b341-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5b341-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5b341-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5b341-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="5b341-116">The call timed out.</span></span>|  
|<span data-ttu-id="5b341-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5b341-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5b341-118">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="5b341-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5b341-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5b341-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5b341-120">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="5b341-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5b341-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5b341-121">E_FAIL</span></span>|<span data-ttu-id="5b341-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="5b341-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5b341-123">Dopo che un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="5b341-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5b341-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5b341-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b341-125">Note</span><span class="sxs-lookup"><span data-stu-id="5b341-125">Remarks</span></span>  
 <span data-ttu-id="5b341-126">Il `Collect` metodo forza il garbage collector di CLR per eseguire una raccolta indipendentemente dallo stato corrente.</span><span class="sxs-lookup"><span data-stu-id="5b341-126">The `Collect` method forces the CLR's garbage collector to perform a collection regardless of its current state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b341-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5b341-127">Requirements</span></span>  
 <span data-ttu-id="5b341-128">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b341-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b341-129">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5b341-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5b341-130">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="5b341-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="5b341-131">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5b341-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5b341-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b341-132">See also</span></span>

- [<span data-ttu-id="5b341-133">Automatic Memory Management</span><span class="sxs-lookup"><span data-stu-id="5b341-133">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="5b341-134">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="5b341-134">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)
- [<span data-ttu-id="5b341-135">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="5b341-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="5b341-136">Interfaccia ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="5b341-136">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="5b341-137">Interfacce di hosting CLR</span><span class="sxs-lookup"><span data-stu-id="5b341-137">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="5b341-138">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="5b341-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="5b341-139">Hosting</span><span class="sxs-lookup"><span data-stu-id="5b341-139">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)

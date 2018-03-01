---
title: Metodo ICLRRuntimeHost::SetHostControl
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
- ICLRRuntimeHost.SetHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::SetHostControl
helpviewer_keywords:
- SetHostControl method [.NET Framework hosting]
- ICLRRuntimeHost::SetHostControl method [.NET Framework hosting]
ms.assetid: 6136be87-e631-4756-81ed-74b66581bad4
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9727144e9504a5a3ad7ae2529286440d07633b2a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimehostsethostcontrol-method"></a><span data-ttu-id="6abed-102">Metodo ICLRRuntimeHost::SetHostControl</span><span class="sxs-lookup"><span data-stu-id="6abed-102">ICLRRuntimeHost::SetHostControl Method</span></span>
<span data-ttu-id="6abed-103">Imposta il puntatore a interfaccia che common language runtime (CLR) consente di ottenere l'implementazione dell'host di [interfaccia IHostControl](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span><span class="sxs-lookup"><span data-stu-id="6abed-103">Sets the interface pointer that the common language runtime (CLR) can use to get the host's implementation of [IHostControl Interface](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6abed-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6abed-104">Syntax</span></span>  
  
```  
HRESULT SetHostControl(  
    [in] IHostControl* pHostControl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6abed-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6abed-105">Parameters</span></span>  
 `pHostControl`  
 <span data-ttu-id="6abed-106">[in] Un puntatore a interfaccia per l'implementazione dell'host di [interfaccia IHostControl](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span><span class="sxs-lookup"><span data-stu-id="6abed-106">[in] An interface pointer to the host's implementation of [IHostControl Interface](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6abed-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6abed-107">Return Value</span></span>  
  
|<span data-ttu-id="6abed-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6abed-108">HRESULT</span></span>|<span data-ttu-id="6abed-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6abed-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6abed-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6abed-110">S_OK</span></span>|<span data-ttu-id="6abed-111">`SetHostControl`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="6abed-111">`SetHostControl` returned successfully.</span></span>|  
|<span data-ttu-id="6abed-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6abed-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6abed-113">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="6abed-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6abed-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6abed-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6abed-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="6abed-115">The call timed out.</span></span>|  
|<span data-ttu-id="6abed-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6abed-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6abed-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="6abed-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6abed-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6abed-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6abed-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="6abed-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6abed-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6abed-120">E_FAIL</span></span>|<span data-ttu-id="6abed-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="6abed-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6abed-122">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="6abed-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6abed-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6abed-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6abed-124">E_CLR_ALREADY_STARTED</span><span class="sxs-lookup"><span data-stu-id="6abed-124">E_CLR_ALREADY_STARTED</span></span>|<span data-ttu-id="6abed-125">CLR è già stato inizializzato.</span><span class="sxs-lookup"><span data-stu-id="6abed-125">The CLR has already been initialized.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6abed-126">Note</span><span class="sxs-lookup"><span data-stu-id="6abed-126">Remarks</span></span>  
 <span data-ttu-id="6abed-127">È necessario chiamare `SetHostControl` prima di CLR viene inizializzato, vale a dire, prima di chiamare [metodo Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) o utilizzare uno qualsiasi del [interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="6abed-127">You must call `SetHostControl` before the CLR is initialized, that is, before you call [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) or use any of the [Metadata Interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span> <span data-ttu-id="6abed-128">È consigliabile chiamare `SetHostControl` immediatamente dopo la chiamata [funzione CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md) o [funzione CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md).</span><span class="sxs-lookup"><span data-stu-id="6abed-128">It is recommended that you call `SetHostControl` immediately after calling [CorBindToCurrentRuntime Function](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md) or [CorBindToRuntimeEx Function](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6abed-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6abed-129">Requirements</span></span>  
 <span data-ttu-id="6abed-130">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6abed-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6abed-131">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="6abed-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6abed-132">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6abed-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6abed-133">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6abed-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6abed-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6abed-134">See Also</span></span>  
 [<span data-ttu-id="6abed-135">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="6abed-135">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [<span data-ttu-id="6abed-136">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="6abed-136">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)

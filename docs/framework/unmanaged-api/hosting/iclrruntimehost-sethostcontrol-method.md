---
title: Metodo ICLRRuntimeHost::SetHostControl
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8400f615f2fcdb847b398806fe4219ae709beebe
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57495299"
---
# <a name="iclrruntimehostsethostcontrol-method"></a><span data-ttu-id="30a42-102">Metodo ICLRRuntimeHost::SetHostControl</span><span class="sxs-lookup"><span data-stu-id="30a42-102">ICLRRuntimeHost::SetHostControl Method</span></span>
<span data-ttu-id="30a42-103">Imposta il puntatore a interfaccia utilizzabile per ottenere l'implementazione dell'host di common language runtime (CLR) [interfaccia IHostControl](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span><span class="sxs-lookup"><span data-stu-id="30a42-103">Sets the interface pointer that the common language runtime (CLR) can use to get the host's implementation of [IHostControl Interface](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30a42-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30a42-104">Syntax</span></span>  
  
```  
HRESULT SetHostControl(  
    [in] IHostControl* pHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30a42-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="30a42-105">Parameters</span></span>  
 `pHostControl`  
 <span data-ttu-id="30a42-106">[in] Un puntatore a interfaccia per l'implementazione di host dei [interfaccia IHostControl](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span><span class="sxs-lookup"><span data-stu-id="30a42-106">[in] An interface pointer to the host's implementation of [IHostControl Interface](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30a42-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="30a42-107">Return Value</span></span>  
  
|<span data-ttu-id="30a42-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="30a42-108">HRESULT</span></span>|<span data-ttu-id="30a42-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="30a42-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="30a42-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="30a42-110">S_OK</span></span>|<span data-ttu-id="30a42-111">`SetHostControl` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="30a42-111">`SetHostControl` returned successfully.</span></span>|  
|<span data-ttu-id="30a42-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="30a42-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="30a42-113">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="30a42-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="30a42-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="30a42-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="30a42-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="30a42-115">The call timed out.</span></span>|  
|<span data-ttu-id="30a42-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="30a42-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="30a42-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="30a42-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="30a42-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="30a42-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="30a42-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="30a42-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="30a42-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="30a42-120">E_FAIL</span></span>|<span data-ttu-id="30a42-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="30a42-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="30a42-122">Se un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="30a42-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="30a42-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="30a42-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="30a42-124">E_CLR_ALREADY_STARTED</span><span class="sxs-lookup"><span data-stu-id="30a42-124">E_CLR_ALREADY_STARTED</span></span>|<span data-ttu-id="30a42-125">CLR è già stato inizializzato.</span><span class="sxs-lookup"><span data-stu-id="30a42-125">The CLR has already been initialized.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30a42-126">Note</span><span class="sxs-lookup"><span data-stu-id="30a42-126">Remarks</span></span>  
 <span data-ttu-id="30a42-127">È necessario chiamare `SetHostControl` prima di CLR viene inizializzato, vale a dire, prima di chiamare [metodo Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) oppure usare uno qualsiasi del [interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="30a42-127">You must call `SetHostControl` before the CLR is initialized, that is, before you call [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) or use any of the [Metadata Interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span> <span data-ttu-id="30a42-128">Si consiglia di chiamare `SetHostControl` immediatamente dopo la chiamata [funzione CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md) oppure [funzione CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md).</span><span class="sxs-lookup"><span data-stu-id="30a42-128">It is recommended that you call `SetHostControl` immediately after calling [CorBindToCurrentRuntime Function](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md) or [CorBindToRuntimeEx Function](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30a42-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="30a42-129">Requirements</span></span>  
 <span data-ttu-id="30a42-130">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30a42-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30a42-131">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="30a42-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="30a42-132">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="30a42-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="30a42-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30a42-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30a42-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30a42-134">See also</span></span>
- [<span data-ttu-id="30a42-135">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="30a42-135">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [<span data-ttu-id="30a42-136">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="30a42-136">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)

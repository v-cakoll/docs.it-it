---
title: Metodo ICLROnEventManager::UnregisterActionOnEvent
ms.date: 03/30/2017
api_name:
- ICLROnEventManager.UnregisterActionOnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager::UnregisterActionOnEvent
helpviewer_keywords:
- UnRegisterActionOnEvent method [.NET Framework hosting]
- ICLROnEventManager::UnRegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: 4c02ec37-cdf0-46b2-890e-235092741236
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e5ebe0ad045c2047ed0756c7efee5f4cfc919c7d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559242"
---
# <a name="iclroneventmanagerunregisteractiononevent-method"></a><span data-ttu-id="326d0-102">Metodo ICLROnEventManager::UnregisterActionOnEvent</span><span class="sxs-lookup"><span data-stu-id="326d0-102">ICLROnEventManager::UnregisterActionOnEvent Method</span></span>
<span data-ttu-id="326d0-103">Annulla la registrazione di un puntatore di callback registrato in precedenza per l'evento specificato.</span><span class="sxs-lookup"><span data-stu-id="326d0-103">Unregisters a previously registered callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="326d0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="326d0-104">Syntax</span></span>  
  
```  
HRESULT UnregisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="326d0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="326d0-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="326d0-106">[in] Uno dei [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) valori, che indica l'evento per cui si desidera annullare la registrazione il puntatore di richiamata descritto da `pAction`.</span><span class="sxs-lookup"><span data-stu-id="326d0-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, indicating the event for which to unregister the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="326d0-107">[in] Un puntatore a un [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) che è stato passato come parametro per il [RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="326d0-107">[in] A pointer to an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) object that was passed as a parameter to the [RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="326d0-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="326d0-108">Return Value</span></span>  
  
|<span data-ttu-id="326d0-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="326d0-109">HRESULT</span></span>|<span data-ttu-id="326d0-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="326d0-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="326d0-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="326d0-111">S_OK</span></span>|<span data-ttu-id="326d0-112">`UnregisterActionOnEvent` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="326d0-112">`UnregisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="326d0-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="326d0-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="326d0-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="326d0-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="326d0-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="326d0-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="326d0-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="326d0-116">The call timed out.</span></span>|  
|<span data-ttu-id="326d0-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="326d0-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="326d0-118">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="326d0-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="326d0-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="326d0-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="326d0-120">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="326d0-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="326d0-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="326d0-121">E_FAIL</span></span>|<span data-ttu-id="326d0-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="326d0-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="326d0-123">Dopo che un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="326d0-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="326d0-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="326d0-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="326d0-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="326d0-125">Requirements</span></span>  
 <span data-ttu-id="326d0-126">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="326d0-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="326d0-127">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="326d0-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="326d0-128">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="326d0-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="326d0-129">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="326d0-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="326d0-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="326d0-130">See also</span></span>
- [<span data-ttu-id="326d0-131">Enumerazione EClrEvent</span><span class="sxs-lookup"><span data-stu-id="326d0-131">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="326d0-132">Interfaccia IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="326d0-132">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="326d0-133">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="326d0-133">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="326d0-134">Interfaccia ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="326d0-134">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)

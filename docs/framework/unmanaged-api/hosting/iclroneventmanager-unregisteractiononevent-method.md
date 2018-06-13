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
ms.openlocfilehash: 7add5e85aac273b4d513a24196af8305082c417f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434650"
---
# <a name="iclroneventmanagerunregisteractiononevent-method"></a><span data-ttu-id="9a012-102">Metodo ICLROnEventManager::UnregisterActionOnEvent</span><span class="sxs-lookup"><span data-stu-id="9a012-102">ICLROnEventManager::UnregisterActionOnEvent Method</span></span>
<span data-ttu-id="9a012-103">Annulla la registrazione di un puntatore di callback registrato in precedenza per l'evento specificato.</span><span class="sxs-lookup"><span data-stu-id="9a012-103">Unregisters a previously registered callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a012-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a012-104">Syntax</span></span>  
  
```  
HRESULT UnregisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a012-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9a012-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="9a012-106">[in] Uno del [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) valori, che indica l'evento per cui si desidera annullare la registrazione del puntatore di callback descritto da `pAction`.</span><span class="sxs-lookup"><span data-stu-id="9a012-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, indicating the event for which to unregister the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="9a012-107">[in] Un puntatore a un [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) oggetto passato come parametro per il [RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="9a012-107">[in] A pointer to an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) object that was passed as a parameter to the [RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a012-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9a012-108">Return Value</span></span>  
  
|<span data-ttu-id="9a012-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9a012-109">HRESULT</span></span>|<span data-ttu-id="9a012-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9a012-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9a012-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="9a012-111">S_OK</span></span>|<span data-ttu-id="9a012-112">`UnregisterActionOnEvent` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="9a012-112">`UnregisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="9a012-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9a012-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9a012-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9a012-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9a012-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9a012-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9a012-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9a012-116">The call timed out.</span></span>|  
|<span data-ttu-id="9a012-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9a012-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9a012-118">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="9a012-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9a012-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9a012-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9a012-120">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="9a012-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9a012-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9a012-121">E_FAIL</span></span>|<span data-ttu-id="9a012-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="9a012-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9a012-123">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="9a012-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9a012-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9a012-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9a012-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9a012-125">Requirements</span></span>  
 <span data-ttu-id="9a012-126">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a012-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a012-127">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="9a012-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9a012-128">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="9a012-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9a012-129">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a012-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a012-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a012-130">See Also</span></span>  
 [<span data-ttu-id="9a012-131">Enumerazione EClrEvent</span><span class="sxs-lookup"><span data-stu-id="9a012-131">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [<span data-ttu-id="9a012-132">Interfaccia IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="9a012-132">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [<span data-ttu-id="9a012-133">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="9a012-133">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="9a012-134">Interfaccia ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="9a012-134">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)

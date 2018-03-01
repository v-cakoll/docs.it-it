---
title: Metodo ICLRTaskManager::SetUILocale
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
- ICLRTaskManager.SetUILocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::SetUILocale
helpviewer_keywords:
- ICLRTaskManager::SetUILocale method [.NET Framework hosting]
- SetUILocale method, ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 03adaa9a-2beb-49b3-b2c4-6b4fc3f10715
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fab9da8f7e63ad000595378f5bc36f3aadc2ac3d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtaskmanagersetuilocale-method"></a><span data-ttu-id="ed19f-102">Metodo ICLRTaskManager::SetUILocale</span><span class="sxs-lookup"><span data-stu-id="ed19f-102">ICLRTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="ed19f-103">Notifica a common language runtime (CLR) che l'host ha modificato le impostazioni locali dell'interfaccia utente o delle impostazioni cultura, l'attività attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ed19f-103">Notifies the common language runtime (CLR) that the host has modified the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed19f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ed19f-104">Syntax</span></span>  
  
```  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ed19f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ed19f-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="ed19f-106">[in] Il valore dell'identificatore delle impostazioni locali che esegue il mapping per le nuove impostazioni e la lingua dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="ed19f-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language for the user interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ed19f-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ed19f-107">Return Value</span></span>  
  
|<span data-ttu-id="ed19f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ed19f-108">HRESULT</span></span>|<span data-ttu-id="ed19f-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ed19f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ed19f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ed19f-110">S_OK</span></span>|<span data-ttu-id="ed19f-111">`SetUILocale`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="ed19f-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="ed19f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ed19f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ed19f-113">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="ed19f-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ed19f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ed19f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ed19f-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="ed19f-115">The call timed out.</span></span>|  
|<span data-ttu-id="ed19f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ed19f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ed19f-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="ed19f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ed19f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ed19f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ed19f-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="ed19f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ed19f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ed19f-120">E_FAIL</span></span>|<span data-ttu-id="ed19f-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="ed19f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ed19f-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="ed19f-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ed19f-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ed19f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed19f-124">Note</span><span class="sxs-lookup"><span data-stu-id="ed19f-124">Remarks</span></span>  
 <span data-ttu-id="ed19f-125">`SetUILocale`fornisce una possibilità per l'host eseguire qualsiasi meccanismi che disponibili per la sincronizzazione delle impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="ed19f-125">`SetUILocale` provides an opportunity for the host to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed19f-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ed19f-126">Requirements</span></span>  
 <span data-ttu-id="ed19f-127">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed19f-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed19f-128">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="ed19f-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ed19f-129">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ed19f-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ed19f-130">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed19f-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed19f-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed19f-131">See Also</span></span>  
 [<span data-ttu-id="ed19f-132">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="ed19f-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="ed19f-133">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="ed19f-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="ed19f-134">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="ed19f-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="ed19f-135">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="ed19f-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

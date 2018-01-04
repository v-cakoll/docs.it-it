---
title: Metodo ICLRTaskManager::SetLocale
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTaskManager.SetLocale
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTaskManager::SetLocale
helpviewer_keywords:
- SetLocale method, ICLRTaskManager interface [.NET Framework hosting]
- ICLRTaskManager::SetLocale method [.NET Framework hosting]
ms.assetid: ed16bb7f-4206-43a8-b9e9-c5737b69e3af
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bbed6bff52d7ccad38eb45d12a31d08dc8b1b774
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtaskmanagersetlocale-method"></a><span data-ttu-id="6dc26-102">Metodo ICLRTaskManager::SetLocale</span><span class="sxs-lookup"><span data-stu-id="6dc26-102">ICLRTaskManager::SetLocale Method</span></span>
<span data-ttu-id="6dc26-103">Notifica a common language runtime (CLR) che l'host ha modificato il valore dell'identificatore delle impostazioni locali (che esegue il mapping alle impostazioni cultura e alla lingua) per l'attività attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6dc26-103">Notifies the common language runtime (CLR) that the host has modified the value of the locale identifier (which maps to the geographical culture and language) on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6dc26-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6dc26-104">Syntax</span></span>  
  
```  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6dc26-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6dc26-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="6dc26-106">[in] Il valore dell'identificatore delle impostazioni locali che esegue il mapping alle nuove impostazioni e alla lingua.</span><span class="sxs-lookup"><span data-stu-id="6dc26-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6dc26-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6dc26-107">Return Value</span></span>  
  
|<span data-ttu-id="6dc26-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6dc26-108">HRESULT</span></span>|<span data-ttu-id="6dc26-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6dc26-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6dc26-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6dc26-110">S_OK</span></span>|<span data-ttu-id="6dc26-111">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="6dc26-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="6dc26-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6dc26-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6dc26-113">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="6dc26-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6dc26-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6dc26-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6dc26-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="6dc26-115">The call timed out.</span></span>|  
|<span data-ttu-id="6dc26-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6dc26-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6dc26-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="6dc26-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6dc26-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6dc26-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6dc26-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="6dc26-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6dc26-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6dc26-120">E_FAIL</span></span>|<span data-ttu-id="6dc26-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="6dc26-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6dc26-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="6dc26-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6dc26-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6dc26-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6dc26-124">Note</span><span class="sxs-lookup"><span data-stu-id="6dc26-124">Remarks</span></span>  
 <span data-ttu-id="6dc26-125">`SetLocale`consente all'host la possibilità di eseguire qualsiasi meccanismi che disponibili per la sincronizzazione delle impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="6dc26-125">`SetLocale` gives the host an opportunity to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6dc26-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6dc26-126">Requirements</span></span>  
 <span data-ttu-id="6dc26-127">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6dc26-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6dc26-128">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="6dc26-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6dc26-129">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6dc26-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6dc26-130">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6dc26-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dc26-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6dc26-131">See Also</span></span>  
 [<span data-ttu-id="6dc26-132">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="6dc26-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="6dc26-133">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="6dc26-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="6dc26-134">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="6dc26-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="6dc26-135">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="6dc26-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

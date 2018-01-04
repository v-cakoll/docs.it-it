---
title: Metodo IHostTaskManager::SetUILocale
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.SetUILocale
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::SetUILocale
helpviewer_keywords:
- SetUILocale method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::SetUILocale method [.NET Framework hosting]
ms.assetid: d0c87a9c-ea81-4237-a16b-c22b36ec9dc8
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 099c3d4878e7dd83be9240e121777c71c2890c88
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanagersetuilocale-method"></a><span data-ttu-id="3bc36-102">Metodo IHostTaskManager::SetUILocale</span><span class="sxs-lookup"><span data-stu-id="3bc36-102">IHostTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="3bc36-103">Notifica all'host che common language runtime (CLR) ha modificato le impostazioni locali dell'interfaccia utente, o le impostazioni cultura, l'attività attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3bc36-103">Notifies the host that the common language runtime (CLR) has changed the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bc36-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3bc36-104">Syntax</span></span>  
  
```  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3bc36-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3bc36-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="3bc36-106">[in] Il valore dell'identificatore delle impostazioni locali che esegue il mapping alle nuove impostazioni e alla lingua.</span><span class="sxs-lookup"><span data-stu-id="3bc36-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3bc36-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3bc36-107">Return Value</span></span>  
  
|<span data-ttu-id="3bc36-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3bc36-108">HRESULT</span></span>|<span data-ttu-id="3bc36-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3bc36-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3bc36-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3bc36-110">S_OK</span></span>|<span data-ttu-id="3bc36-111">`SetUILocale`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="3bc36-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="3bc36-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3bc36-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3bc36-113">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="3bc36-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3bc36-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3bc36-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3bc36-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="3bc36-115">The call timed out.</span></span>|  
|<span data-ttu-id="3bc36-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3bc36-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3bc36-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="3bc36-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3bc36-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3bc36-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3bc36-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="3bc36-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3bc36-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3bc36-120">E_FAIL</span></span>|<span data-ttu-id="3bc36-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="3bc36-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3bc36-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="3bc36-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3bc36-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3bc36-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3bc36-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="3bc36-124">E_NOTIMPL</span></span>|<span data-ttu-id="3bc36-125">L'host non consente il codice utente gestito modificare le impostazioni cultura dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="3bc36-125">The host does not allow managed user code to change the UI culture.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3bc36-126">Note</span><span class="sxs-lookup"><span data-stu-id="3bc36-126">Remarks</span></span>  
 <span data-ttu-id="3bc36-127">Il runtime chiama `SetUILocale` quando il valore di <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> proprietà viene modificata dal codice gestito.</span><span class="sxs-lookup"><span data-stu-id="3bc36-127">The runtime calls `SetUILocale` when the value of the <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="3bc36-128">Questo metodo fornisce una possibilità per l'host di eseguire qualsiasi meccanismi che disponibili per la sincronizzazione delle impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="3bc36-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="3bc36-129">Se un host non consente le impostazioni locali dell'interfaccia utente essere modificato dal codice gestito o non implementa un meccanismo per la sincronizzazione delle impostazioni locali, da questo metodo deve restituire E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="3bc36-129">If a host does not allow the UI locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bc36-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3bc36-130">Requirements</span></span>  
 <span data-ttu-id="3bc36-131">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3bc36-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bc36-132">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="3bc36-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3bc36-133">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3bc36-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3bc36-134">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bc36-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bc36-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3bc36-135">See Also</span></span>  
 [<span data-ttu-id="3bc36-136">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="3bc36-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="3bc36-137">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="3bc36-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="3bc36-138">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="3bc36-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="3bc36-139">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="3bc36-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="3bc36-140">Metodo SetLocale</span><span class="sxs-lookup"><span data-stu-id="3bc36-140">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)

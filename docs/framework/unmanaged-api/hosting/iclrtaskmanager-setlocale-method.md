---
title: Metodo ICLRTaskManager::SetLocale
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.SetLocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::SetLocale
helpviewer_keywords:
- SetLocale method, ICLRTaskManager interface [.NET Framework hosting]
- ICLRTaskManager::SetLocale method [.NET Framework hosting]
ms.assetid: ed16bb7f-4206-43a8-b9e9-c5737b69e3af
topic_type:
- apiref
ms.openlocfilehash: 79f24b3ccacd84037042a883d3a034bb7b4d200a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092085"
---
# <a name="iclrtaskmanagersetlocale-method"></a><span data-ttu-id="92dd2-102">Metodo ICLRTaskManager::SetLocale</span><span class="sxs-lookup"><span data-stu-id="92dd2-102">ICLRTaskManager::SetLocale Method</span></span>
<span data-ttu-id="92dd2-103">Notifica al Common Language Runtime (CLR) che l'host ha modificato il valore dell'identificatore delle impostazioni locali (che esegue il mapping alla lingua e alle impostazioni cultura geografiche) nell'attività attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="92dd2-103">Notifies the common language runtime (CLR) that the host has modified the value of the locale identifier (which maps to the geographical culture and language) on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92dd2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="92dd2-104">Syntax</span></span>  
  
```cpp  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92dd2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="92dd2-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="92dd2-106">in Valore dell'identificatore delle impostazioni locali mappato alle impostazioni cultura e alla lingua geografiche appena assegnate.</span><span class="sxs-lookup"><span data-stu-id="92dd2-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="92dd2-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="92dd2-107">Return Value</span></span>  
  
|<span data-ttu-id="92dd2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="92dd2-108">HRESULT</span></span>|<span data-ttu-id="92dd2-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="92dd2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="92dd2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="92dd2-110">S_OK</span></span>|<span data-ttu-id="92dd2-111">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="92dd2-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="92dd2-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="92dd2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="92dd2-113">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="92dd2-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="92dd2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="92dd2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="92dd2-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="92dd2-115">The call timed out.</span></span>|  
|<span data-ttu-id="92dd2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="92dd2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="92dd2-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="92dd2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="92dd2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="92dd2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="92dd2-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="92dd2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="92dd2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="92dd2-120">E_FAIL</span></span>|<span data-ttu-id="92dd2-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="92dd2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="92dd2-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="92dd2-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="92dd2-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="92dd2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92dd2-124">Note</span><span class="sxs-lookup"><span data-stu-id="92dd2-124">Remarks</span></span>  
 <span data-ttu-id="92dd2-125">`SetLocale` offre all'host la possibilità di eseguire tutti i meccanismi che potrebbero avere per la sincronizzazione delle impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="92dd2-125">`SetLocale` gives the host an opportunity to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92dd2-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="92dd2-126">Requirements</span></span>  
 <span data-ttu-id="92dd2-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92dd2-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92dd2-128">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="92dd2-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="92dd2-129">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="92dd2-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="92dd2-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92dd2-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92dd2-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92dd2-131">See also</span></span>

- [<span data-ttu-id="92dd2-132">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="92dd2-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="92dd2-133">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="92dd2-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="92dd2-134">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="92dd2-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="92dd2-135">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="92dd2-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

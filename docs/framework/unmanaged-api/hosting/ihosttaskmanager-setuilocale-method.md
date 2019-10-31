---
title: Metodo IHostTaskManager::SetUILocale
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetUILocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetUILocale
helpviewer_keywords:
- SetUILocale method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::SetUILocale method [.NET Framework hosting]
ms.assetid: d0c87a9c-ea81-4237-a16b-c22b36ec9dc8
topic_type:
- apiref
ms.openlocfilehash: a929a125fc8c70744246f4f96d8a09a4605f537c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132937"
---
# <a name="ihosttaskmanagersetuilocale-method"></a><span data-ttu-id="09ce3-102">Metodo IHostTaskManager::SetUILocale</span><span class="sxs-lookup"><span data-stu-id="09ce3-102">IHostTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="09ce3-103">Notifica all'host che la Common Language Runtime (CLR) ha modificato le impostazioni locali dell'interfaccia utente (UI) o le impostazioni cultura nell'attività attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="09ce3-103">Notifies the host that the common language runtime (CLR) has changed the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09ce3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="09ce3-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09ce3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="09ce3-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="09ce3-106">in Valore dell'identificatore delle impostazioni locali mappato alle impostazioni cultura e alla lingua geografiche appena assegnate.</span><span class="sxs-lookup"><span data-stu-id="09ce3-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09ce3-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="09ce3-107">Return Value</span></span>  
  
|<span data-ttu-id="09ce3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="09ce3-108">HRESULT</span></span>|<span data-ttu-id="09ce3-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="09ce3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="09ce3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="09ce3-110">S_OK</span></span>|<span data-ttu-id="09ce3-111">`SetUILocale` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="09ce3-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="09ce3-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="09ce3-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="09ce3-113">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="09ce3-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="09ce3-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="09ce3-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="09ce3-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="09ce3-115">The call timed out.</span></span>|  
|<span data-ttu-id="09ce3-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="09ce3-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="09ce3-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="09ce3-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="09ce3-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="09ce3-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="09ce3-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="09ce3-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="09ce3-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="09ce3-120">E_FAIL</span></span>|<span data-ttu-id="09ce3-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="09ce3-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="09ce3-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="09ce3-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="09ce3-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="09ce3-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="09ce3-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="09ce3-124">E_NOTIMPL</span></span>|<span data-ttu-id="09ce3-125">L'host non consente al codice utente gestito di modificare le impostazioni cultura dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="09ce3-125">The host does not allow managed user code to change the UI culture.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09ce3-126">Note</span><span class="sxs-lookup"><span data-stu-id="09ce3-126">Remarks</span></span>  
 <span data-ttu-id="09ce3-127">Il runtime chiama `SetUILocale` quando il valore della proprietà <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> viene modificato dal codice gestito.</span><span class="sxs-lookup"><span data-stu-id="09ce3-127">The runtime calls `SetUILocale` when the value of the <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="09ce3-128">Questo metodo consente all'host di eseguire tutti i meccanismi che potrebbero avere per la sincronizzazione delle impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="09ce3-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="09ce3-129">Se un host non consente la modifica delle impostazioni locali dell'interfaccia utente dal codice gestito o non implementa un meccanismo per sincronizzare le impostazioni locali, deve restituire E_NOTIMPL da questo metodo.</span><span class="sxs-lookup"><span data-stu-id="09ce3-129">If a host does not allow the UI locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09ce3-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="09ce3-130">Requirements</span></span>  
 <span data-ttu-id="09ce3-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09ce3-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09ce3-132">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="09ce3-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="09ce3-133">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="09ce3-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="09ce3-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09ce3-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09ce3-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09ce3-135">See also</span></span>

- [<span data-ttu-id="09ce3-136">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="09ce3-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="09ce3-137">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="09ce3-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="09ce3-138">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="09ce3-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="09ce3-139">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="09ce3-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="09ce3-140">Metodo SetLocale</span><span class="sxs-lookup"><span data-stu-id="09ce3-140">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)

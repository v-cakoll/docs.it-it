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
ms.openlocfilehash: e7e65c3b9bcafdf4c8b1185fcff1fc0740b2ef7c
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2020
ms.locfileid: "83841432"
---
# <a name="ihosttaskmanagersetuilocale-method"></a><span data-ttu-id="5fa90-102">Metodo IHostTaskManager::SetUILocale</span><span class="sxs-lookup"><span data-stu-id="5fa90-102">IHostTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="5fa90-103">Notifica all'host che la Common Language Runtime (CLR) ha modificato le impostazioni locali dell'interfaccia utente (UI) o le impostazioni cultura nell'attività attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5fa90-103">Notifies the host that the common language runtime (CLR) has changed the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fa90-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5fa90-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5fa90-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5fa90-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="5fa90-106">in Valore dell'identificatore delle impostazioni locali mappato alle impostazioni cultura e alla lingua geografiche appena assegnate.</span><span class="sxs-lookup"><span data-stu-id="5fa90-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5fa90-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5fa90-107">Return Value</span></span>  
  
|<span data-ttu-id="5fa90-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5fa90-108">HRESULT</span></span>|<span data-ttu-id="5fa90-109">Description</span><span class="sxs-lookup"><span data-stu-id="5fa90-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5fa90-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5fa90-110">S_OK</span></span>|<span data-ttu-id="5fa90-111">`SetUILocale`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="5fa90-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="5fa90-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5fa90-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5fa90-113">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="5fa90-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5fa90-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5fa90-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5fa90-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="5fa90-115">The call timed out.</span></span>|  
|<span data-ttu-id="5fa90-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5fa90-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5fa90-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="5fa90-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5fa90-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5fa90-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5fa90-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="5fa90-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5fa90-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5fa90-120">E_FAIL</span></span>|<span data-ttu-id="5fa90-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="5fa90-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5fa90-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="5fa90-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5fa90-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5fa90-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5fa90-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="5fa90-124">E_NOTIMPL</span></span>|<span data-ttu-id="5fa90-125">L'host non consente al codice utente gestito di modificare le impostazioni cultura dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="5fa90-125">The host does not allow managed user code to change the UI culture.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5fa90-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5fa90-126">Remarks</span></span>  
 <span data-ttu-id="5fa90-127">Il runtime chiama `SetUILocale` quando il valore della <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> proprietà viene modificato dal codice gestito.</span><span class="sxs-lookup"><span data-stu-id="5fa90-127">The runtime calls `SetUILocale` when the value of the <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="5fa90-128">Questo metodo consente all'host di eseguire tutti i meccanismi che potrebbero avere per la sincronizzazione delle impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="5fa90-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="5fa90-129">Se un host non consente la modifica delle impostazioni locali dell'interfaccia utente dal codice gestito o non implementa un meccanismo per sincronizzare le impostazioni locali, deve restituire E_NOTIMPL da questo metodo.</span><span class="sxs-lookup"><span data-stu-id="5fa90-129">If a host does not allow the UI locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fa90-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5fa90-130">Requirements</span></span>  
 <span data-ttu-id="5fa90-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fa90-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fa90-132">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5fa90-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5fa90-133">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5fa90-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5fa90-134">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fa90-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fa90-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5fa90-135">See also</span></span>

- [<span data-ttu-id="5fa90-136">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="5fa90-136">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="5fa90-137">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="5fa90-137">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="5fa90-138">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="5fa90-138">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="5fa90-139">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="5fa90-139">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="5fa90-140">Metodo SetLocale</span><span class="sxs-lookup"><span data-stu-id="5fa90-140">SetLocale Method</span></span>](ihosttaskmanager-setlocale-method.md)

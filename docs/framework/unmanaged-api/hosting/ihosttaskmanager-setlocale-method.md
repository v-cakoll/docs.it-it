---
title: Metodo IHostTaskManager::SetLocale
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetLocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetLocale
helpviewer_keywords:
- SetLocale method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::SetLocale method [.NET Framework hosting]
ms.assetid: 747ee407-ee8c-484d-9583-25089236d2d1
topic_type:
- apiref
ms.openlocfilehash: 841827017262b731fd5e6f6bd0b5862fecaf2744
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2020
ms.locfileid: "83841724"
---
# <a name="ihosttaskmanagersetlocale-method"></a><span data-ttu-id="50ba7-102">Metodo IHostTaskManager::SetLocale</span><span class="sxs-lookup"><span data-stu-id="50ba7-102">IHostTaskManager::SetLocale Method</span></span>
<span data-ttu-id="50ba7-103">Notifica all'host che la Common Language Runtime (CLR) ha modificato le impostazioni locali o le impostazioni cultura nell'attività attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="50ba7-103">Notifies the host that the common language runtime (CLR) has changed the locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50ba7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="50ba7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50ba7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="50ba7-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="50ba7-106">in Valore dell'identificatore delle impostazioni locali mappato alle impostazioni cultura e alla lingua geografiche appena assegnate.</span><span class="sxs-lookup"><span data-stu-id="50ba7-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="50ba7-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="50ba7-107">Return Value</span></span>  
  
|<span data-ttu-id="50ba7-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="50ba7-108">HRESULT</span></span>|<span data-ttu-id="50ba7-109">Description</span><span class="sxs-lookup"><span data-stu-id="50ba7-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="50ba7-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="50ba7-110">S_OK</span></span>|<span data-ttu-id="50ba7-111">`SetLocale`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="50ba7-111">`SetLocale` returned successfully.</span></span>|  
|<span data-ttu-id="50ba7-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="50ba7-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="50ba7-113">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="50ba7-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="50ba7-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="50ba7-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="50ba7-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="50ba7-115">The call timed out.</span></span>|  
|<span data-ttu-id="50ba7-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="50ba7-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="50ba7-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="50ba7-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="50ba7-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="50ba7-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="50ba7-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="50ba7-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="50ba7-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="50ba7-120">E_FAIL</span></span>|<span data-ttu-id="50ba7-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="50ba7-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="50ba7-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="50ba7-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="50ba7-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="50ba7-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="50ba7-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="50ba7-124">E_NOTIMPL</span></span>|<span data-ttu-id="50ba7-125">L'host non consente al codice utente gestito di modificare le impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="50ba7-125">The host does not allow managed user code to modify the locale.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50ba7-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="50ba7-126">Remarks</span></span>  
 <span data-ttu-id="50ba7-127">Il runtime chiama `SetLocale` quando il valore della <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> proprietà viene modificato dal codice gestito.</span><span class="sxs-lookup"><span data-stu-id="50ba7-127">The runtime calls `SetLocale` when the value of the <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="50ba7-128">Questo metodo consente all'host di eseguire tutti i meccanismi che potrebbero avere per la sincronizzazione delle impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="50ba7-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="50ba7-129">Se un host non consente la modifica delle impostazioni locali dal codice gestito o non implementa un meccanismo per sincronizzare le impostazioni locali, deve restituire E_NOTIMPL da questo metodo.</span><span class="sxs-lookup"><span data-stu-id="50ba7-129">If a host does not allow the locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50ba7-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="50ba7-130">Requirements</span></span>  
 <span data-ttu-id="50ba7-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50ba7-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50ba7-132">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="50ba7-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="50ba7-133">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="50ba7-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="50ba7-134">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50ba7-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50ba7-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50ba7-135">See also</span></span>

- [<span data-ttu-id="50ba7-136">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="50ba7-136">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="50ba7-137">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="50ba7-137">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="50ba7-138">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="50ba7-138">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="50ba7-139">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="50ba7-139">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="50ba7-140">Metodo SetUILocale</span><span class="sxs-lookup"><span data-stu-id="50ba7-140">SetUILocale Method</span></span>](ihosttaskmanager-setuilocale-method.md)

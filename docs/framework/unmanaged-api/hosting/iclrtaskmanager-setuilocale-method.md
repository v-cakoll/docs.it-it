---
title: Metodo ICLRTaskManager::SetUILocale
ms.date: 03/30/2017
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
ms.openlocfilehash: 051bd5cb846eb4e6e3390e17b3011a1c5b50bc45
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127871"
---
# <a name="iclrtaskmanagersetuilocale-method"></a><span data-ttu-id="eeca6-102">Metodo ICLRTaskManager::SetUILocale</span><span class="sxs-lookup"><span data-stu-id="eeca6-102">ICLRTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="eeca6-103">Notifica al Common Language Runtime (CLR) che l'host ha modificato le impostazioni locali dell'interfaccia utente (UI) o le impostazioni cultura nell'attività attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="eeca6-103">Notifies the common language runtime (CLR) that the host has modified the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eeca6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eeca6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eeca6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="eeca6-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="eeca6-106">in Valore dell'identificatore delle impostazioni locali mappato alle impostazioni cultura e alla lingua geografica appena assegnate per l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="eeca6-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language for the user interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eeca6-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="eeca6-107">Return Value</span></span>  
  
|<span data-ttu-id="eeca6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="eeca6-108">HRESULT</span></span>|<span data-ttu-id="eeca6-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eeca6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eeca6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="eeca6-110">S_OK</span></span>|<span data-ttu-id="eeca6-111">`SetUILocale` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="eeca6-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="eeca6-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="eeca6-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="eeca6-113">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="eeca6-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="eeca6-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="eeca6-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="eeca6-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="eeca6-115">The call timed out.</span></span>|  
|<span data-ttu-id="eeca6-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="eeca6-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="eeca6-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="eeca6-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="eeca6-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="eeca6-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="eeca6-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="eeca6-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="eeca6-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="eeca6-120">E_FAIL</span></span>|<span data-ttu-id="eeca6-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="eeca6-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="eeca6-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="eeca6-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="eeca6-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="eeca6-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eeca6-124">Note</span><span class="sxs-lookup"><span data-stu-id="eeca6-124">Remarks</span></span>  
 <span data-ttu-id="eeca6-125">`SetUILocale` consente all'host di eseguire tutti i meccanismi che potrebbero avere per la sincronizzazione delle impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="eeca6-125">`SetUILocale` provides an opportunity for the host to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eeca6-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="eeca6-126">Requirements</span></span>  
 <span data-ttu-id="eeca6-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eeca6-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eeca6-128">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="eeca6-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eeca6-129">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="eeca6-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eeca6-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eeca6-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeca6-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eeca6-131">See also</span></span>

- [<span data-ttu-id="eeca6-132">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="eeca6-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="eeca6-133">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="eeca6-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="eeca6-134">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="eeca6-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="eeca6-135">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="eeca6-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

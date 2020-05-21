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
ms.openlocfilehash: 8f316d91aab4c3862a0ad45b41539a4b80791ab9
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762791"
---
# <a name="iclrtaskmanagersetlocale-method"></a><span data-ttu-id="f17db-102">Metodo ICLRTaskManager::SetLocale</span><span class="sxs-lookup"><span data-stu-id="f17db-102">ICLRTaskManager::SetLocale Method</span></span>
<span data-ttu-id="f17db-103">Notifica al Common Language Runtime (CLR) che l'host ha modificato il valore dell'identificatore delle impostazioni locali (che esegue il mapping alla lingua e alle impostazioni cultura geografiche) nell'attività attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f17db-103">Notifies the common language runtime (CLR) that the host has modified the value of the locale identifier (which maps to the geographical culture and language) on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f17db-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f17db-104">Syntax</span></span>  
  
```cpp  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f17db-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f17db-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="f17db-106">in Valore dell'identificatore delle impostazioni locali mappato alle impostazioni cultura e alla lingua geografiche appena assegnate.</span><span class="sxs-lookup"><span data-stu-id="f17db-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f17db-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f17db-107">Return Value</span></span>  
  
|<span data-ttu-id="f17db-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f17db-108">HRESULT</span></span>|<span data-ttu-id="f17db-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f17db-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f17db-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f17db-110">S_OK</span></span>|<span data-ttu-id="f17db-111">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="f17db-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="f17db-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f17db-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f17db-113">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="f17db-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f17db-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f17db-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f17db-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f17db-115">The call timed out.</span></span>|  
|<span data-ttu-id="f17db-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f17db-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f17db-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="f17db-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f17db-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f17db-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f17db-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="f17db-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f17db-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f17db-120">E_FAIL</span></span>|<span data-ttu-id="f17db-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="f17db-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f17db-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="f17db-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f17db-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f17db-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f17db-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f17db-124">Remarks</span></span>  
 <span data-ttu-id="f17db-125">`SetLocale`offre all'host la possibilità di eseguire qualsiasi meccanismo per la sincronizzazione delle impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="f17db-125">`SetLocale` gives the host an opportunity to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f17db-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f17db-126">Requirements</span></span>  
 <span data-ttu-id="f17db-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f17db-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f17db-128">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f17db-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f17db-129">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f17db-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f17db-130">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f17db-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f17db-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f17db-131">See also</span></span>

- [<span data-ttu-id="f17db-132">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="f17db-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="f17db-133">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="f17db-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="f17db-134">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="f17db-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="f17db-135">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="f17db-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)

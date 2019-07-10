---
title: Metodo IHostTaskManager::Sleep
ms.date: 03/30/2017
api_name:
- IHostTaskManager.Sleep
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::Sleep
helpviewer_keywords:
- IHostTaskManager::Sleep method [.NET Framework hosting]
- Sleep method, IHostTaskManager interface [.NET Framework hosting]
ms.assetid: f67d25f3-9199-4c5f-b1e8-1c819243cfd5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e25f2e49ab25d2df827fdd59526b13976d21219
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756562"
---
# <a name="ihosttaskmanagersleep-method"></a><span data-ttu-id="aca33-102">Metodo IHostTaskManager::Sleep</span><span class="sxs-lookup"><span data-stu-id="aca33-102">IHostTaskManager::Sleep Method</span></span>
<span data-ttu-id="aca33-103">Notifica all'host che l'attività corrente verrà sospeso.</span><span class="sxs-lookup"><span data-stu-id="aca33-103">Notifies the host that the current task is going to sleep.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aca33-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aca33-104">Syntax</span></span>  
  
```cpp  
HRESULT Sleep (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aca33-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="aca33-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="aca33-106">[in] L'intervallo di tempo, espresso in millisecondi, che rimarrà in sospensione di thread.</span><span class="sxs-lookup"><span data-stu-id="aca33-106">[in] The time interval, in milliseconds, that the thread will sleep.</span></span>  
  
 `option`  
 <span data-ttu-id="aca33-107">[in] Uno del [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valori di enumerazione, che indica l'azione che l'host deve intraprendere se l'operazione.</span><span class="sxs-lookup"><span data-stu-id="aca33-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) enumeration values, indicating what action the host should take if this action blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aca33-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="aca33-108">Return Value</span></span>  
  
|<span data-ttu-id="aca33-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="aca33-109">HRESULT</span></span>|<span data-ttu-id="aca33-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aca33-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="aca33-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="aca33-111">S_OK</span></span>|<span data-ttu-id="aca33-112">`Sleep` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="aca33-112">`Sleep` returned successfully.</span></span>|  
|<span data-ttu-id="aca33-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="aca33-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="aca33-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="aca33-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="aca33-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="aca33-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="aca33-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="aca33-116">The call timed out.</span></span>|  
|<span data-ttu-id="aca33-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="aca33-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="aca33-118">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="aca33-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="aca33-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="aca33-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="aca33-120">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="aca33-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="aca33-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="aca33-121">E_FAIL</span></span>|<span data-ttu-id="aca33-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="aca33-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="aca33-123">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="aca33-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="aca33-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="aca33-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aca33-125">Note</span><span class="sxs-lookup"><span data-stu-id="aca33-125">Remarks</span></span>  
 <span data-ttu-id="aca33-126">CLR chiama in genere `IHostTaskManager::Sleep` quando <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> viene chiamato dal codice utente.</span><span class="sxs-lookup"><span data-stu-id="aca33-126">The CLR typically calls `IHostTaskManager::Sleep` when <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> is called from user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aca33-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="aca33-127">Requirements</span></span>  
 <span data-ttu-id="aca33-128">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aca33-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aca33-129">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="aca33-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aca33-130">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="aca33-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aca33-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aca33-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aca33-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aca33-132">See also</span></span>

- [<span data-ttu-id="aca33-133">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="aca33-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="aca33-134">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="aca33-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="aca33-135">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="aca33-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="aca33-136">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="aca33-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

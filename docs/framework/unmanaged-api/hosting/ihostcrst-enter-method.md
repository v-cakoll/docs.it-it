---
title: Metodo IHostCrst::Enter
ms.date: 03/30/2017
api_name:
- IHostCrst.Enter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::Enter
helpviewer_keywords:
- Enter method [.NET Framework hosting]
- IHostCrst::Enter method [.NET Framework hosting]
ms.assetid: 100dd7eb-7053-4295-9bb3-32ba47f6ec79
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bdc597e741023af1c7cc1f48e378083157dd4a5d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937745"
---
# <a name="ihostcrstenter-method"></a><span data-ttu-id="3eb8a-102">Metodo IHostCrst::Enter</span><span class="sxs-lookup"><span data-stu-id="3eb8a-102">IHostCrst::Enter Method</span></span>
<span data-ttu-id="3eb8a-103">Immette la sezione critica rappresentata dall'istanza corrente di [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="3eb8a-103">Enters the critical section that is represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3eb8a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3eb8a-104">Syntax</span></span>  
  
```cpp  
HRESULT Enter (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3eb8a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3eb8a-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="3eb8a-106">in Uno dei valori di [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) , che indica l'azione che l'host deve eseguire se l'operazione si blocca.</span><span class="sxs-lookup"><span data-stu-id="3eb8a-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3eb8a-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3eb8a-107">Return Value</span></span>  
  
|<span data-ttu-id="3eb8a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3eb8a-108">HRESULT</span></span>|<span data-ttu-id="3eb8a-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3eb8a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3eb8a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3eb8a-110">S_OK</span></span>|<span data-ttu-id="3eb8a-111">`Enter`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="3eb8a-111">`Enter` returned successfully.</span></span>|  
|<span data-ttu-id="3eb8a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3eb8a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3eb8a-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="3eb8a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3eb8a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3eb8a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3eb8a-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="3eb8a-115">The call timed out.</span></span>|  
|<span data-ttu-id="3eb8a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3eb8a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3eb8a-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="3eb8a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3eb8a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3eb8a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3eb8a-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="3eb8a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3eb8a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3eb8a-120">E_FAIL</span></span>|<span data-ttu-id="3eb8a-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="3eb8a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3eb8a-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="3eb8a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3eb8a-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3eb8a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3eb8a-124">Note</span><span class="sxs-lookup"><span data-stu-id="3eb8a-124">Remarks</span></span>  
 <span data-ttu-id="3eb8a-125">`Enter`rispecchia la funzione `EnterCriticalSection` Win32.</span><span class="sxs-lookup"><span data-stu-id="3eb8a-125">`Enter` mirrors the Win32 `EnterCriticalSection` function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3eb8a-126">Questo metodo non restituisce alcun risultato finché non viene immessa la sezione critica.</span><span class="sxs-lookup"><span data-stu-id="3eb8a-126">This method does not return until the critical section is entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3eb8a-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3eb8a-127">Requirements</span></span>  
 <span data-ttu-id="3eb8a-128">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3eb8a-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3eb8a-129">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3eb8a-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3eb8a-130">**Libreria** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3eb8a-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3eb8a-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3eb8a-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eb8a-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3eb8a-132">See also</span></span>

- [<span data-ttu-id="3eb8a-133">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="3eb8a-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="3eb8a-134">Interfaccia IHostCrst</span><span class="sxs-lookup"><span data-stu-id="3eb8a-134">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="3eb8a-135">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="3eb8a-135">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)

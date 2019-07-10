---
title: Metodo IHostCrst::TryEnter
ms.date: 03/30/2017
api_name:
- IHostCrst.TryEnter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::TryEnter
helpviewer_keywords:
- IHostCrst::TryEnter method [.NET Framework hosting]
- TryEnter method [.NET Framework hosting]
ms.assetid: a922fa98-beab-4f09-a342-cc94fc65687f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d0b4074d9dab8ad46468930373ad44b0c72bd690
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763748"
---
# <a name="ihostcrsttryenter-method"></a><span data-ttu-id="28a5a-102">Metodo IHostCrst::TryEnter</span><span class="sxs-lookup"><span data-stu-id="28a5a-102">IHostCrst::TryEnter Method</span></span>
<span data-ttu-id="28a5a-103">Tenta di accedere alla sezione critica rappresentata dall'oggetto corrente [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) istanza.</span><span class="sxs-lookup"><span data-stu-id="28a5a-103">Attempts to enter the critical section represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28a5a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="28a5a-104">Syntax</span></span>  
  
```cpp  
HRESULT TryEnter (  
    [in]  DWORD  option,  
    [out] BOOL   *pbSucceeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28a5a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="28a5a-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="28a5a-106">[in] Uno dei [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valori, che indica l'azione che l'host deve intraprendere se l'operazione si blocca.</span><span class="sxs-lookup"><span data-stu-id="28a5a-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
 `pbSucceeded`  
 <span data-ttu-id="28a5a-107">[out] `true` se la sezione critica può essere immesso; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="28a5a-107">[out] `true` if the critical section can be entered; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="28a5a-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="28a5a-108">Return Value</span></span>  
  
|<span data-ttu-id="28a5a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="28a5a-109">HRESULT</span></span>|<span data-ttu-id="28a5a-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="28a5a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="28a5a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="28a5a-111">S_OK</span></span>|<span data-ttu-id="28a5a-112">`TryEnter` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="28a5a-112">`TryEnter` returned successfully.</span></span>|  
|<span data-ttu-id="28a5a-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="28a5a-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="28a5a-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="28a5a-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="28a5a-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="28a5a-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="28a5a-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="28a5a-116">The call timed out.</span></span>|  
|<span data-ttu-id="28a5a-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="28a5a-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="28a5a-118">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="28a5a-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="28a5a-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="28a5a-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="28a5a-120">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="28a5a-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="28a5a-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="28a5a-121">E_FAIL</span></span>|<span data-ttu-id="28a5a-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="28a5a-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="28a5a-123">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="28a5a-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="28a5a-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="28a5a-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28a5a-125">Note</span><span class="sxs-lookup"><span data-stu-id="28a5a-125">Remarks</span></span>  
 <span data-ttu-id="28a5a-126">`TryEnter` restituisce immediatamente e indica se il thread chiamante è passato alla sezione critica.</span><span class="sxs-lookup"><span data-stu-id="28a5a-126">`TryEnter` returns immediately and indicates whether the calling thread entered the critical section.</span></span> <span data-ttu-id="28a5a-127">Questo metodo rispecchia il Wind32 `TryEnterCriticalSection` (funzione).</span><span class="sxs-lookup"><span data-stu-id="28a5a-127">This method mirrors the Wind32 `TryEnterCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28a5a-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="28a5a-128">Requirements</span></span>  
 <span data-ttu-id="28a5a-129">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28a5a-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28a5a-130">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="28a5a-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="28a5a-131">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="28a5a-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="28a5a-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28a5a-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28a5a-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28a5a-133">See also</span></span>

- [<span data-ttu-id="28a5a-134">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="28a5a-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="28a5a-135">Interfaccia IHostCrst</span><span class="sxs-lookup"><span data-stu-id="28a5a-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="28a5a-136">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="28a5a-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)

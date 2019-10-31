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
ms.openlocfilehash: f4b40a595bbdea4dd390a42af6a0d4b1a5efa2f2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130501"
---
# <a name="ihostcrsttryenter-method"></a><span data-ttu-id="9fca1-102">Metodo IHostCrst::TryEnter</span><span class="sxs-lookup"><span data-stu-id="9fca1-102">IHostCrst::TryEnter Method</span></span>
<span data-ttu-id="9fca1-103">Tenta di immettere la sezione critica rappresentata dall'istanza corrente di [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="9fca1-103">Attempts to enter the critical section represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fca1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9fca1-104">Syntax</span></span>  
  
```cpp  
HRESULT TryEnter (  
    [in]  DWORD  option,  
    [out] BOOL   *pbSucceeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9fca1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9fca1-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="9fca1-106">in Uno dei valori di [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) , che indica l'azione che l'host deve eseguire se l'operazione si blocca.</span><span class="sxs-lookup"><span data-stu-id="9fca1-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
 `pbSucceeded`  
 <span data-ttu-id="9fca1-107">[out] `true` se è possibile immettere la sezione critica; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="9fca1-107">[out] `true` if the critical section can be entered; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9fca1-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9fca1-108">Return Value</span></span>  
  
|<span data-ttu-id="9fca1-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9fca1-109">HRESULT</span></span>|<span data-ttu-id="9fca1-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9fca1-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9fca1-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="9fca1-111">S_OK</span></span>|<span data-ttu-id="9fca1-112">`TryEnter` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9fca1-112">`TryEnter` returned successfully.</span></span>|  
|<span data-ttu-id="9fca1-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9fca1-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9fca1-114">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="9fca1-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9fca1-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9fca1-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9fca1-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9fca1-116">The call timed out.</span></span>|  
|<span data-ttu-id="9fca1-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9fca1-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9fca1-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="9fca1-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9fca1-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9fca1-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9fca1-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="9fca1-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9fca1-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9fca1-121">E_FAIL</span></span>|<span data-ttu-id="9fca1-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="9fca1-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9fca1-123">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="9fca1-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9fca1-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9fca1-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9fca1-125">Note</span><span class="sxs-lookup"><span data-stu-id="9fca1-125">Remarks</span></span>  
 <span data-ttu-id="9fca1-126">`TryEnter` restituisce immediatamente un valore e indica se il thread chiamante è entrato nella sezione critica.</span><span class="sxs-lookup"><span data-stu-id="9fca1-126">`TryEnter` returns immediately and indicates whether the calling thread entered the critical section.</span></span> <span data-ttu-id="9fca1-127">Questo metodo rispecchia la funzione Wind32 `TryEnterCriticalSection`.</span><span class="sxs-lookup"><span data-stu-id="9fca1-127">This method mirrors the Wind32 `TryEnterCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fca1-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9fca1-128">Requirements</span></span>  
 <span data-ttu-id="9fca1-129">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9fca1-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fca1-130">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9fca1-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9fca1-131">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9fca1-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9fca1-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fca1-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fca1-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9fca1-133">See also</span></span>

- [<span data-ttu-id="9fca1-134">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="9fca1-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="9fca1-135">Interfaccia IHostCrst</span><span class="sxs-lookup"><span data-stu-id="9fca1-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="9fca1-136">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="9fca1-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)

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
ms.openlocfilehash: a472b686799bfec4b53b8880a0c52c6f0846b03a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442377"
---
# <a name="ihostcrstenter-method"></a><span data-ttu-id="9b08d-102">Metodo IHostCrst::Enter</span><span class="sxs-lookup"><span data-stu-id="9b08d-102">IHostCrst::Enter Method</span></span>
<span data-ttu-id="9b08d-103">Entra nella sezione critica è rappresentata dall'oggetto corrente [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) istanza.</span><span class="sxs-lookup"><span data-stu-id="9b08d-103">Enters the critical section that is represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b08d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9b08d-104">Syntax</span></span>  
  
```  
HRESULT Enter (  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9b08d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9b08d-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="9b08d-106">[in] Uno del [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valori, che indica l'azione che l'operazione si blocca.</span><span class="sxs-lookup"><span data-stu-id="9b08d-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b08d-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9b08d-107">Return Value</span></span>  
  
|<span data-ttu-id="9b08d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9b08d-108">HRESULT</span></span>|<span data-ttu-id="9b08d-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9b08d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9b08d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9b08d-110">S_OK</span></span>|<span data-ttu-id="9b08d-111">`Enter` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="9b08d-111">`Enter` returned successfully.</span></span>|  
|<span data-ttu-id="9b08d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9b08d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9b08d-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9b08d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9b08d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9b08d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9b08d-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9b08d-115">The call timed out.</span></span>|  
|<span data-ttu-id="9b08d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9b08d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9b08d-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="9b08d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9b08d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9b08d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9b08d-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="9b08d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9b08d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9b08d-120">E_FAIL</span></span>|<span data-ttu-id="9b08d-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="9b08d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9b08d-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="9b08d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9b08d-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9b08d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b08d-124">Note</span><span class="sxs-lookup"><span data-stu-id="9b08d-124">Remarks</span></span>  
 <span data-ttu-id="9b08d-125">`Enter` esegue il mirroring Win32 `EnterCriticalSection` (funzione).</span><span class="sxs-lookup"><span data-stu-id="9b08d-125">`Enter` mirrors the Win32 `EnterCriticalSection` function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9b08d-126">Questo metodo non restituisce fino a quando non viene immesso nella sezione critica.</span><span class="sxs-lookup"><span data-stu-id="9b08d-126">This method does not return until the critical section is entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b08d-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9b08d-127">Requirements</span></span>  
 <span data-ttu-id="9b08d-128">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b08d-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b08d-129">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="9b08d-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9b08d-130">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="9b08d-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9b08d-131">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b08d-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b08d-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b08d-132">See Also</span></span>  
 [<span data-ttu-id="9b08d-133">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="9b08d-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="9b08d-134">Interfaccia IHostCrst</span><span class="sxs-lookup"><span data-stu-id="9b08d-134">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 [<span data-ttu-id="9b08d-135">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="9b08d-135">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)

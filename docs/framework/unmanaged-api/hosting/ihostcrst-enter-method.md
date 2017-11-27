---
title: Metodo IHostCrst::Enter
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostCrst.Enter
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostCrst::Enter
helpviewer_keywords:
- Enter method [.NET Framework hosting]
- IHostCrst::Enter method [.NET Framework hosting]
ms.assetid: 100dd7eb-7053-4295-9bb3-32ba47f6ec79
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9d209e13360616295f166ad23c65b0c4e764af79
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostcrstenter-method"></a><span data-ttu-id="622be-102">Metodo IHostCrst::Enter</span><span class="sxs-lookup"><span data-stu-id="622be-102">IHostCrst::Enter Method</span></span>
<span data-ttu-id="622be-103">Entra nella sezione critica è rappresentata dall'oggetto corrente [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) istanza.</span><span class="sxs-lookup"><span data-stu-id="622be-103">Enters the critical section that is represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="622be-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="622be-104">Syntax</span></span>  
  
```  
HRESULT Enter (  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="622be-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="622be-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="622be-106">[in] Uno del [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valori, che indica l'azione che l'operazione si blocca.</span><span class="sxs-lookup"><span data-stu-id="622be-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="622be-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="622be-107">Return Value</span></span>  
  
|<span data-ttu-id="622be-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="622be-108">HRESULT</span></span>|<span data-ttu-id="622be-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="622be-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="622be-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="622be-110">S_OK</span></span>|<span data-ttu-id="622be-111">`Enter`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="622be-111">`Enter` returned successfully.</span></span>|  
|<span data-ttu-id="622be-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="622be-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="622be-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="622be-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="622be-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="622be-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="622be-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="622be-115">The call timed out.</span></span>|  
|<span data-ttu-id="622be-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="622be-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="622be-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="622be-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="622be-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="622be-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="622be-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="622be-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="622be-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="622be-120">E_FAIL</span></span>|<span data-ttu-id="622be-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="622be-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="622be-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="622be-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="622be-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="622be-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="622be-124">Note</span><span class="sxs-lookup"><span data-stu-id="622be-124">Remarks</span></span>  
 <span data-ttu-id="622be-125">`Enter`rispecchia Win32 `EnterCriticalSection` (funzione).</span><span class="sxs-lookup"><span data-stu-id="622be-125">`Enter` mirrors the Win32 `EnterCriticalSection` function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="622be-126">Questo metodo non restituisce fino a quando non viene immesso nella sezione critica.</span><span class="sxs-lookup"><span data-stu-id="622be-126">This method does not return until the critical section is entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="622be-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="622be-127">Requirements</span></span>  
 <span data-ttu-id="622be-128">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="622be-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="622be-129">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="622be-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="622be-130">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="622be-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="622be-131">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="622be-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="622be-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="622be-132">See Also</span></span>  
 [<span data-ttu-id="622be-133">ICLRSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="622be-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="622be-134">IHostCrst (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="622be-134">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 [<span data-ttu-id="622be-135">IHostSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="622be-135">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)

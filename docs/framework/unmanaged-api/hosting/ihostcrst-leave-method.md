---
title: Metodo IHostCrst::Leave
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostCrst.Leave
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostCrst::Leave
helpviewer_keywords:
- IHostCrst::Leave method [.NET Framework hosting]
- Leave method [.NET Framework hosting]
ms.assetid: dfc51d9e-b36d-4dba-9ea1-4f63fa0601ae
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 391aff3920e7ea2ef010ce7d97bdedb4e636dc86
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ihostcrstleave-method"></a><span data-ttu-id="5935a-102">Metodo IHostCrst::Leave</span><span class="sxs-lookup"><span data-stu-id="5935a-102">IHostCrst::Leave Method</span></span>
<span data-ttu-id="5935a-103">Esce dalla sezione critica rappresentata dall'istanza corrente di [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md).</span><span class="sxs-lookup"><span data-stu-id="5935a-103">Leaves the critical section that is represented by the current instance of [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5935a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5935a-104">Syntax</span></span>  
  
```  
HRESULT Leave ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5935a-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5935a-105">Return Value</span></span>  
  
|<span data-ttu-id="5935a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5935a-106">HRESULT</span></span>|<span data-ttu-id="5935a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5935a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5935a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="5935a-108">S_OK</span></span>|<span data-ttu-id="5935a-109">`Leave`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="5935a-109">`Leave` returned successfully.</span></span>|  
|<span data-ttu-id="5935a-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5935a-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5935a-111">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="5935a-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5935a-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5935a-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5935a-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="5935a-113">The call timed out.</span></span>|  
|<span data-ttu-id="5935a-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5935a-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5935a-115">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="5935a-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5935a-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5935a-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5935a-117">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="5935a-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5935a-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5935a-118">E_FAIL</span></span>|<span data-ttu-id="5935a-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="5935a-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5935a-120">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="5935a-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5935a-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5935a-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5935a-122">Note</span><span class="sxs-lookup"><span data-stu-id="5935a-122">Remarks</span></span>  
 <span data-ttu-id="5935a-123">`Leave`consente a CLR comunicare direttamente con l'host implementazione threading, anziché utilizzare Win32 corrispondente `LeaveCriticalSection` (funzione).</span><span class="sxs-lookup"><span data-stu-id="5935a-123">`Leave` allows the CLR to communicate directly with the host's threading implementation, rather than using the corresponding Win32 `LeaveCriticalSection` function.</span></span> <span data-ttu-id="5935a-124">Un thread che acquisisce la proprietà della sezione critica rappresentata dall'oggetto corrente `IHostCrst` istanza è necessario chiamare `Leave` una volta per ogni volta che accede alla sezione critica.</span><span class="sxs-lookup"><span data-stu-id="5935a-124">A thread that takes ownership of the critical section represented by the current `IHostCrst` instance must call `Leave` once for each time it enters that critical section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5935a-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5935a-125">Requirements</span></span>  
 <span data-ttu-id="5935a-126">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5935a-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5935a-127">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="5935a-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5935a-128">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5935a-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5935a-129">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5935a-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5935a-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5935a-130">See Also</span></span>  
 [<span data-ttu-id="5935a-131">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="5935a-131">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="5935a-132">Interfaccia IHostCrst</span><span class="sxs-lookup"><span data-stu-id="5935a-132">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 [<span data-ttu-id="5935a-133">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="5935a-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)

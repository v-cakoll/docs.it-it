---
title: Metodo IHostCrst::Leave
ms.date: 03/30/2017
api_name:
- IHostCrst.Leave
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::Leave
helpviewer_keywords:
- IHostCrst::Leave method [.NET Framework hosting]
- Leave method [.NET Framework hosting]
ms.assetid: dfc51d9e-b36d-4dba-9ea1-4f63fa0601ae
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e474a3cf92e818a3e58f4e97786c17af336fa791
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549928"
---
# <a name="ihostcrstleave-method"></a><span data-ttu-id="b9239-102">Metodo IHostCrst::Leave</span><span class="sxs-lookup"><span data-stu-id="b9239-102">IHostCrst::Leave Method</span></span>
<span data-ttu-id="b9239-103">Esce dalla sezione critica rappresentato dall'istanza corrente di [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md).</span><span class="sxs-lookup"><span data-stu-id="b9239-103">Leaves the critical section that is represented by the current instance of [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9239-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b9239-104">Syntax</span></span>  
  
```  
HRESULT Leave ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="b9239-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b9239-105">Return Value</span></span>  
  
|<span data-ttu-id="b9239-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b9239-106">HRESULT</span></span>|<span data-ttu-id="b9239-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b9239-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b9239-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="b9239-108">S_OK</span></span>|<span data-ttu-id="b9239-109">`Leave` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="b9239-109">`Leave` returned successfully.</span></span>|  
|<span data-ttu-id="b9239-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b9239-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b9239-111">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b9239-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b9239-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b9239-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b9239-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b9239-113">The call timed out.</span></span>|  
|<span data-ttu-id="b9239-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b9239-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b9239-115">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="b9239-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b9239-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b9239-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b9239-117">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="b9239-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b9239-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b9239-118">E_FAIL</span></span>|<span data-ttu-id="b9239-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="b9239-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b9239-120">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="b9239-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b9239-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b9239-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9239-122">Note</span><span class="sxs-lookup"><span data-stu-id="b9239-122">Remarks</span></span>  
 <span data-ttu-id="b9239-123">`Leave` consente a CLR comunicare direttamente con l'host implementazione threading, anziché utilizzare Win32 corrispondente `LeaveCriticalSection` (funzione).</span><span class="sxs-lookup"><span data-stu-id="b9239-123">`Leave` allows the CLR to communicate directly with the host's threading implementation, rather than using the corresponding Win32 `LeaveCriticalSection` function.</span></span> <span data-ttu-id="b9239-124">Un thread che acquisisce la proprietà della sezione critica rappresentata dall'oggetto corrente `IHostCrst` istanza deve chiamare `Leave` una volta per ogni volta che tale sezione critica.</span><span class="sxs-lookup"><span data-stu-id="b9239-124">A thread that takes ownership of the critical section represented by the current `IHostCrst` instance must call `Leave` once for each time it enters that critical section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9239-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b9239-125">Requirements</span></span>  
 <span data-ttu-id="b9239-126">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9239-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9239-127">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b9239-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b9239-128">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="b9239-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b9239-129">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9239-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9239-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9239-130">See also</span></span>
- [<span data-ttu-id="b9239-131">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="b9239-131">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="b9239-132">Interfaccia IHostCrst</span><span class="sxs-lookup"><span data-stu-id="b9239-132">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="b9239-133">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="b9239-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)

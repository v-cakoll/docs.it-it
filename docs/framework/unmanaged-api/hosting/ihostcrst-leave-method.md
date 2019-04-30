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
ms.openlocfilehash: 2d60cdee0a5357f7e117dc902b073049f3bbaea9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61984386"
---
# <a name="ihostcrstleave-method"></a><span data-ttu-id="171c7-102">Metodo IHostCrst::Leave</span><span class="sxs-lookup"><span data-stu-id="171c7-102">IHostCrst::Leave Method</span></span>
<span data-ttu-id="171c7-103">Esce dalla sezione critica rappresentato dall'istanza corrente di [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md).</span><span class="sxs-lookup"><span data-stu-id="171c7-103">Leaves the critical section that is represented by the current instance of [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="171c7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="171c7-104">Syntax</span></span>  
  
```  
HRESULT Leave ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="171c7-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="171c7-105">Return Value</span></span>  
  
|<span data-ttu-id="171c7-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="171c7-106">HRESULT</span></span>|<span data-ttu-id="171c7-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="171c7-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="171c7-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="171c7-108">S_OK</span></span>|<span data-ttu-id="171c7-109">`Leave` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="171c7-109">`Leave` returned successfully.</span></span>|  
|<span data-ttu-id="171c7-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="171c7-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="171c7-111">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="171c7-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="171c7-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="171c7-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="171c7-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="171c7-113">The call timed out.</span></span>|  
|<span data-ttu-id="171c7-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="171c7-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="171c7-115">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="171c7-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="171c7-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="171c7-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="171c7-117">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="171c7-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="171c7-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="171c7-118">E_FAIL</span></span>|<span data-ttu-id="171c7-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="171c7-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="171c7-120">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="171c7-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="171c7-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="171c7-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="171c7-122">Note</span><span class="sxs-lookup"><span data-stu-id="171c7-122">Remarks</span></span>  
 <span data-ttu-id="171c7-123">`Leave` consente a CLR comunicare direttamente con l'host implementazione threading, anziché utilizzare Win32 corrispondente `LeaveCriticalSection` (funzione).</span><span class="sxs-lookup"><span data-stu-id="171c7-123">`Leave` allows the CLR to communicate directly with the host's threading implementation, rather than using the corresponding Win32 `LeaveCriticalSection` function.</span></span> <span data-ttu-id="171c7-124">Un thread che acquisisce la proprietà della sezione critica rappresentata dall'oggetto corrente `IHostCrst` istanza deve chiamare `Leave` una volta per ogni volta che tale sezione critica.</span><span class="sxs-lookup"><span data-stu-id="171c7-124">A thread that takes ownership of the critical section represented by the current `IHostCrst` instance must call `Leave` once for each time it enters that critical section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="171c7-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="171c7-125">Requirements</span></span>  
 <span data-ttu-id="171c7-126">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="171c7-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="171c7-127">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="171c7-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="171c7-128">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="171c7-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="171c7-129">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="171c7-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="171c7-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="171c7-130">See also</span></span>

- [<span data-ttu-id="171c7-131">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="171c7-131">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="171c7-132">Interfaccia IHostCrst</span><span class="sxs-lookup"><span data-stu-id="171c7-132">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="171c7-133">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="171c7-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)

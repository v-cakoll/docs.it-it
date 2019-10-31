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
ms.openlocfilehash: 050af068579d84b984ed83377d0c201e281bd154
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130538"
---
# <a name="ihostcrstleave-method"></a><span data-ttu-id="04265-102">Metodo IHostCrst::Leave</span><span class="sxs-lookup"><span data-stu-id="04265-102">IHostCrst::Leave Method</span></span>
<span data-ttu-id="04265-103">Lascia la sezione critica rappresentata dall'istanza corrente di [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md).</span><span class="sxs-lookup"><span data-stu-id="04265-103">Leaves the critical section that is represented by the current instance of [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04265-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="04265-104">Syntax</span></span>  
  
```cpp  
HRESULT Leave ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="04265-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="04265-105">Return Value</span></span>  
  
|<span data-ttu-id="04265-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="04265-106">HRESULT</span></span>|<span data-ttu-id="04265-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="04265-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="04265-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="04265-108">S_OK</span></span>|<span data-ttu-id="04265-109">`Leave` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="04265-109">`Leave` returned successfully.</span></span>|  
|<span data-ttu-id="04265-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="04265-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="04265-111">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="04265-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="04265-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="04265-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="04265-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="04265-113">The call timed out.</span></span>|  
|<span data-ttu-id="04265-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="04265-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="04265-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="04265-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="04265-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="04265-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="04265-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="04265-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="04265-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="04265-118">E_FAIL</span></span>|<span data-ttu-id="04265-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="04265-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="04265-120">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="04265-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="04265-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="04265-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04265-122">Note</span><span class="sxs-lookup"><span data-stu-id="04265-122">Remarks</span></span>  
 <span data-ttu-id="04265-123">`Leave` consente a CLR di comunicare direttamente con l'implementazione del threading dell'host, anziché utilizzare la funzione Win32 `LeaveCriticalSection` corrispondente.</span><span class="sxs-lookup"><span data-stu-id="04265-123">`Leave` allows the CLR to communicate directly with the host's threading implementation, rather than using the corresponding Win32 `LeaveCriticalSection` function.</span></span> <span data-ttu-id="04265-124">Un thread che acquisisce la proprietà della sezione critica rappresentata dall'istanza di `IHostCrst` corrente deve chiamare `Leave` una volta per ogni volta che accede alla sezione critica.</span><span class="sxs-lookup"><span data-stu-id="04265-124">A thread that takes ownership of the critical section represented by the current `IHostCrst` instance must call `Leave` once for each time it enters that critical section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04265-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="04265-125">Requirements</span></span>  
 <span data-ttu-id="04265-126">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04265-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04265-127">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="04265-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="04265-128">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="04265-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="04265-129">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04265-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04265-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04265-130">See also</span></span>

- [<span data-ttu-id="04265-131">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="04265-131">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="04265-132">Interfaccia IHostCrst</span><span class="sxs-lookup"><span data-stu-id="04265-132">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="04265-133">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="04265-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)

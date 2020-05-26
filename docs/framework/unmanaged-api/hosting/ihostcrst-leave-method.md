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
ms.openlocfilehash: 08af77c3a158b97cd698dbaeebdc7cdf1b9acfc3
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804888"
---
# <a name="ihostcrstleave-method"></a><span data-ttu-id="23b72-102">Metodo IHostCrst::Leave</span><span class="sxs-lookup"><span data-stu-id="23b72-102">IHostCrst::Leave Method</span></span>
<span data-ttu-id="23b72-103">Lascia la sezione critica rappresentata dall'istanza corrente di [IHostCrst](ihostcrst-interface.md).</span><span class="sxs-lookup"><span data-stu-id="23b72-103">Leaves the critical section that is represented by the current instance of [IHostCrst](ihostcrst-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23b72-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="23b72-104">Syntax</span></span>  
  
```cpp  
HRESULT Leave ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="23b72-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="23b72-105">Return Value</span></span>  
  
|<span data-ttu-id="23b72-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="23b72-106">HRESULT</span></span>|<span data-ttu-id="23b72-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23b72-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="23b72-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="23b72-108">S_OK</span></span>|<span data-ttu-id="23b72-109">`Leave`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="23b72-109">`Leave` returned successfully.</span></span>|  
|<span data-ttu-id="23b72-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="23b72-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="23b72-111">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="23b72-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="23b72-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="23b72-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="23b72-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="23b72-113">The call timed out.</span></span>|  
|<span data-ttu-id="23b72-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="23b72-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="23b72-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="23b72-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="23b72-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="23b72-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="23b72-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="23b72-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="23b72-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="23b72-118">E_FAIL</span></span>|<span data-ttu-id="23b72-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="23b72-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="23b72-120">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="23b72-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="23b72-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="23b72-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23b72-122">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="23b72-122">Remarks</span></span>  
 <span data-ttu-id="23b72-123">`Leave`consente a CLR di comunicare direttamente con l'implementazione del threading dell'host, anziché utilizzare la funzione Win32 corrispondente `LeaveCriticalSection` .</span><span class="sxs-lookup"><span data-stu-id="23b72-123">`Leave` allows the CLR to communicate directly with the host's threading implementation, rather than using the corresponding Win32 `LeaveCriticalSection` function.</span></span> <span data-ttu-id="23b72-124">Un thread che acquisisce la proprietà della sezione critica rappresentata dall' `IHostCrst` istanza corrente deve chiamare `Leave` una volta per ogni volta che accede alla sezione critica.</span><span class="sxs-lookup"><span data-stu-id="23b72-124">A thread that takes ownership of the critical section represented by the current `IHostCrst` instance must call `Leave` once for each time it enters that critical section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23b72-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="23b72-125">Requirements</span></span>  
 <span data-ttu-id="23b72-126">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23b72-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23b72-127">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="23b72-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="23b72-128">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="23b72-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="23b72-129">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23b72-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23b72-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23b72-130">See also</span></span>

- [<span data-ttu-id="23b72-131">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="23b72-131">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="23b72-132">Interfaccia IHostCrst</span><span class="sxs-lookup"><span data-stu-id="23b72-132">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="23b72-133">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="23b72-133">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)

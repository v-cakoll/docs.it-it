---
title: Interfaccia IHostCrst
ms.date: 03/30/2017
api_name:
- IHostCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst
helpviewer_keywords:
- IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type:
- apiref
ms.openlocfilehash: 108492ba298e9f8429b2acd890ab3404365bc602
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130519"
---
# <a name="ihostcrst-interface"></a><span data-ttu-id="31a34-102">Interfaccia IHostCrst</span><span class="sxs-lookup"><span data-stu-id="31a34-102">IHostCrst Interface</span></span>
<span data-ttu-id="31a34-103">Funge da rappresentazione dell'host di una sezione critica per il Threading.</span><span class="sxs-lookup"><span data-stu-id="31a34-103">Serves as the host's representation of a critical section for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="31a34-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="31a34-104">Methods</span></span>  
  
|<span data-ttu-id="31a34-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="31a34-105">Method</span></span>|<span data-ttu-id="31a34-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="31a34-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="31a34-107">Metodo Enter</span><span class="sxs-lookup"><span data-stu-id="31a34-107">Enter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|<span data-ttu-id="31a34-108">Immette la sezione critica.</span><span class="sxs-lookup"><span data-stu-id="31a34-108">Enters the critical section.</span></span>|  
|[<span data-ttu-id="31a34-109">Metodo Leave</span><span class="sxs-lookup"><span data-stu-id="31a34-109">Leave Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|<span data-ttu-id="31a34-110">Lascia la sezione critica.</span><span class="sxs-lookup"><span data-stu-id="31a34-110">Leaves the critical section.</span></span>|  
|[<span data-ttu-id="31a34-111">Metodo SetSpinCount</span><span class="sxs-lookup"><span data-stu-id="31a34-111">SetSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|<span data-ttu-id="31a34-112">Imposta il numero di spin per la sezione critica.</span><span class="sxs-lookup"><span data-stu-id="31a34-112">Sets the spin count for the critical section.</span></span>|  
|[<span data-ttu-id="31a34-113">Metodo TryEnter</span><span class="sxs-lookup"><span data-stu-id="31a34-113">TryEnter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|<span data-ttu-id="31a34-114">Tenta di immettere la sezione critica e segnala immediatamente l'esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="31a34-114">Attempts to enter the critical section, and reports success or failure immediately.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31a34-115">Note</span><span class="sxs-lookup"><span data-stu-id="31a34-115">Remarks</span></span>  
 <span data-ttu-id="31a34-116">`IHostCrst` consente al Common Language Runtime (CLR) di comunicare direttamente con la rappresentazione dell'host di una sezione critica, anziché usare funzioni Win32 come `EnterCriticalSection` o `LeaveCriticalSection`.</span><span class="sxs-lookup"><span data-stu-id="31a34-116">`IHostCrst` allows the common language runtime (CLR) to communicate directly with the host's representation of a critical section, rather than using Win32 functions such as `EnterCriticalSection` or `LeaveCriticalSection`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31a34-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="31a34-117">Requirements</span></span>  
 <span data-ttu-id="31a34-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31a34-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31a34-119">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="31a34-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="31a34-120">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="31a34-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="31a34-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31a34-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31a34-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31a34-122">See also</span></span>

- [<span data-ttu-id="31a34-123">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="31a34-123">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="31a34-124">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="31a34-124">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="31a34-125">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="31a34-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

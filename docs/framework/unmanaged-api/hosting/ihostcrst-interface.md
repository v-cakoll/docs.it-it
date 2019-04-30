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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 939f100e8ee386642a29c33827a8339caf0467b9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967830"
---
# <a name="ihostcrst-interface"></a><span data-ttu-id="92f9b-102">Interfaccia IHostCrst</span><span class="sxs-lookup"><span data-stu-id="92f9b-102">IHostCrst Interface</span></span>
<span data-ttu-id="92f9b-103">Serve come rappresentazione di una sezione critica per il threading dall'host.</span><span class="sxs-lookup"><span data-stu-id="92f9b-103">Serves as the host's representation of a critical section for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="92f9b-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="92f9b-104">Methods</span></span>  
  
|<span data-ttu-id="92f9b-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="92f9b-105">Method</span></span>|<span data-ttu-id="92f9b-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="92f9b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="92f9b-107">Metodo Enter</span><span class="sxs-lookup"><span data-stu-id="92f9b-107">Enter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|<span data-ttu-id="92f9b-108">Entra nella sezione critica.</span><span class="sxs-lookup"><span data-stu-id="92f9b-108">Enters the critical section.</span></span>|  
|[<span data-ttu-id="92f9b-109">Metodo Leave</span><span class="sxs-lookup"><span data-stu-id="92f9b-109">Leave Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|<span data-ttu-id="92f9b-110">Esce dalla sezione critica.</span><span class="sxs-lookup"><span data-stu-id="92f9b-110">Leaves the critical section.</span></span>|  
|[<span data-ttu-id="92f9b-111">Metodo SetSpinCount</span><span class="sxs-lookup"><span data-stu-id="92f9b-111">SetSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|<span data-ttu-id="92f9b-112">Imposta il conteggio della rotazione della sezione critica.</span><span class="sxs-lookup"><span data-stu-id="92f9b-112">Sets the spin count for the critical section.</span></span>|  
|[<span data-ttu-id="92f9b-113">Metodo TryEnter</span><span class="sxs-lookup"><span data-stu-id="92f9b-113">TryEnter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|<span data-ttu-id="92f9b-114">Tenta di accedere immediatamente la sezione critica e report esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="92f9b-114">Attempts to enter the critical section, and reports success or failure immediately.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92f9b-115">Note</span><span class="sxs-lookup"><span data-stu-id="92f9b-115">Remarks</span></span>  
 <span data-ttu-id="92f9b-116">`IHostCrst` consente a common language runtime (CLR) per comunicare direttamente con rappresentazione dell'host di una sezione critica, invece di usare le funzioni Win32, ad esempio `EnterCriticalSection` o `LeaveCriticalSection`.</span><span class="sxs-lookup"><span data-stu-id="92f9b-116">`IHostCrst` allows the common language runtime (CLR) to communicate directly with the host's representation of a critical section, rather than using Win32 functions such as `EnterCriticalSection` or `LeaveCriticalSection`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92f9b-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="92f9b-117">Requirements</span></span>  
 <span data-ttu-id="92f9b-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92f9b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92f9b-119">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="92f9b-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="92f9b-120">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="92f9b-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="92f9b-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92f9b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92f9b-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92f9b-122">See also</span></span>

- [<span data-ttu-id="92f9b-123">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="92f9b-123">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="92f9b-124">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="92f9b-124">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="92f9b-125">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="92f9b-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

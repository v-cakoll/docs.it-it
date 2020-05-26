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
ms.openlocfilehash: e8cb1486ccea11ba6edcf7bbb781a9bf210b496d
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804907"
---
# <a name="ihostcrst-interface"></a><span data-ttu-id="b8bae-102">Interfaccia IHostCrst</span><span class="sxs-lookup"><span data-stu-id="b8bae-102">IHostCrst Interface</span></span>
<span data-ttu-id="b8bae-103">Funge da rappresentazione dell'host di una sezione critica per il Threading.</span><span class="sxs-lookup"><span data-stu-id="b8bae-103">Serves as the host's representation of a critical section for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b8bae-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="b8bae-104">Methods</span></span>  
  
|<span data-ttu-id="b8bae-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="b8bae-105">Method</span></span>|<span data-ttu-id="b8bae-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b8bae-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b8bae-107">Metodo Enter</span><span class="sxs-lookup"><span data-stu-id="b8bae-107">Enter Method</span></span>](ihostcrst-enter-method.md)|<span data-ttu-id="b8bae-108">Immette la sezione critica.</span><span class="sxs-lookup"><span data-stu-id="b8bae-108">Enters the critical section.</span></span>|  
|[<span data-ttu-id="b8bae-109">Metodo Leave</span><span class="sxs-lookup"><span data-stu-id="b8bae-109">Leave Method</span></span>](ihostcrst-leave-method.md)|<span data-ttu-id="b8bae-110">Lascia la sezione critica.</span><span class="sxs-lookup"><span data-stu-id="b8bae-110">Leaves the critical section.</span></span>|  
|[<span data-ttu-id="b8bae-111">Metodo SetSpinCount</span><span class="sxs-lookup"><span data-stu-id="b8bae-111">SetSpinCount Method</span></span>](ihostcrst-setspincount-method.md)|<span data-ttu-id="b8bae-112">Imposta il numero di spin per la sezione critica.</span><span class="sxs-lookup"><span data-stu-id="b8bae-112">Sets the spin count for the critical section.</span></span>|  
|[<span data-ttu-id="b8bae-113">Metodo TryEnter</span><span class="sxs-lookup"><span data-stu-id="b8bae-113">TryEnter Method</span></span>](ihostcrst-tryenter-method.md)|<span data-ttu-id="b8bae-114">Tenta di immettere la sezione critica e segnala immediatamente l'esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="b8bae-114">Attempts to enter the critical section, and reports success or failure immediately.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8bae-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b8bae-115">Remarks</span></span>  
 <span data-ttu-id="b8bae-116">`IHostCrst`consente all'Common Language Runtime (CLR) di comunicare direttamente con la rappresentazione dell'host di una sezione critica, anziché usare funzioni Win32 come `EnterCriticalSection` o `LeaveCriticalSection` .</span><span class="sxs-lookup"><span data-stu-id="b8bae-116">`IHostCrst` allows the common language runtime (CLR) to communicate directly with the host's representation of a critical section, rather than using Win32 functions such as `EnterCriticalSection` or `LeaveCriticalSection`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8bae-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b8bae-117">Requirements</span></span>  
 <span data-ttu-id="b8bae-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8bae-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8bae-119">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b8bae-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b8bae-120">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b8bae-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b8bae-121">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8bae-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8bae-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8bae-122">See also</span></span>

- [<span data-ttu-id="b8bae-123">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="b8bae-123">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="b8bae-124">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="b8bae-124">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="b8bae-125">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="b8bae-125">Hosting Interfaces</span></span>](hosting-interfaces.md)

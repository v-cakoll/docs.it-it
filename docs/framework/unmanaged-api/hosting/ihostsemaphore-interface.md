---
title: Interfaccia IHostSemaphore
ms.date: 03/30/2017
api_name:
- IHostSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore
helpviewer_keywords:
- IHostSemaphore interface [.NET Framework hosting]
ms.assetid: c0765321-656c-441e-bab5-58176292be1e
topic_type:
- apiref
ms.openlocfilehash: 8345d85502087568cb05dd262cccf181e3ca07ac
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803696"
---
# <a name="ihostsemaphore-interface"></a><span data-ttu-id="a458c-102">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="a458c-102">IHostSemaphore Interface</span></span>
<span data-ttu-id="a458c-103">Rappresenta l'implementazione dell'host di un semaforo per il Threading.</span><span class="sxs-lookup"><span data-stu-id="a458c-103">Represents the host's implementation of a semaphore for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a458c-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="a458c-104">Methods</span></span>  
  
|<span data-ttu-id="a458c-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="a458c-105">Method</span></span>|<span data-ttu-id="a458c-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a458c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a458c-107">Metodo ReleaseSemaphore</span><span class="sxs-lookup"><span data-stu-id="a458c-107">ReleaseSemaphore Method</span></span>](ihostsemaphore-releasesemaphore-method.md)|<span data-ttu-id="a458c-108">Aumenta il numero dell'istanza corrente `IHostSemaphore` in base al valore specificato.</span><span class="sxs-lookup"><span data-stu-id="a458c-108">Increases the count of the current `IHostSemaphore` instance by the specified amount.</span></span>|  
|[<span data-ttu-id="a458c-109">Metodo Wait</span><span class="sxs-lookup"><span data-stu-id="a458c-109">Wait Method</span></span>](ihostsemaphore-wait-method.md)|<span data-ttu-id="a458c-110">Fa `IHostSemaphore` in modo che l'istanza corrente attenda finché non è di proprietà o la quantità di tempo specificata scade.</span><span class="sxs-lookup"><span data-stu-id="a458c-110">Causes the current `IHostSemaphore` instance to wait until it is owned or the specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a458c-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a458c-111">Requirements</span></span>  
 <span data-ttu-id="a458c-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a458c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a458c-113">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a458c-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a458c-114">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a458c-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a458c-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a458c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a458c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a458c-116">See also</span></span>

- [<span data-ttu-id="a458c-117">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="a458c-117">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="a458c-118">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="a458c-118">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="a458c-119">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="a458c-119">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="a458c-120">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="a458c-120">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="a458c-121">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="a458c-121">Hosting Interfaces</span></span>](hosting-interfaces.md)

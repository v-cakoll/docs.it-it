---
title: Interfaccia IHostManualEvent
ms.date: 03/30/2017
api_name:
- IHostManualEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent
helpviewer_keywords:
- IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 300c2661-b7d1-4c39-b080-9ebdef0fd523
topic_type:
- apiref
ms.openlocfilehash: 8eba189d6dfca3781c28631a72a9af3c037efeda
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136791"
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="13547-102">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="13547-102">IHostManualEvent Interface</span></span>
<span data-ttu-id="13547-103">Fornisce l'implementazione dell'host di una rappresentazione di un evento di reimpostazione manuale.</span><span class="sxs-lookup"><span data-stu-id="13547-103">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="13547-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="13547-104">Methods</span></span>  
  
|<span data-ttu-id="13547-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="13547-105">Method</span></span>|<span data-ttu-id="13547-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="13547-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="13547-107">Metodo Reset</span><span class="sxs-lookup"><span data-stu-id="13547-107">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)|<span data-ttu-id="13547-108">Reimposta l'istanza corrente di `IHostManualEvent` su uno stato non segnalato.</span><span class="sxs-lookup"><span data-stu-id="13547-108">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="13547-109">Metodo Set</span><span class="sxs-lookup"><span data-stu-id="13547-109">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-set-method.md)|<span data-ttu-id="13547-110">Imposta l'istanza corrente di `IHostManualEvent` su uno stato segnalato.</span><span class="sxs-lookup"><span data-stu-id="13547-110">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="13547-111">Metodo Wait</span><span class="sxs-lookup"><span data-stu-id="13547-111">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-wait-method.md)|<span data-ttu-id="13547-112">Fa in modo che l'istanza corrente di `IHostManualEvent` attenda fino a quando non è di proprietà o che trascorre un intervallo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="13547-112">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="13547-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="13547-113">Requirements</span></span>  
 <span data-ttu-id="13547-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13547-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13547-115">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="13547-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="13547-116">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="13547-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="13547-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13547-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13547-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13547-118">See also</span></span>

- [<span data-ttu-id="13547-119">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="13547-119">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="13547-120">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="13547-120">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="13547-121">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="13547-121">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="13547-122">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="13547-122">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="13547-123">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="13547-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

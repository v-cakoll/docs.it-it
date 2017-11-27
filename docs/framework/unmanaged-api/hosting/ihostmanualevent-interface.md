---
title: Interfaccia IHostManualEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostManualEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostManualEvent
helpviewer_keywords: IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 300c2661-b7d1-4c39-b080-9ebdef0fd523
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5c19125d96d5f4a9e91fc083d53f36ebebd2c569
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="a2299-102">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="a2299-102">IHostManualEvent Interface</span></span>
<span data-ttu-id="a2299-103">Fornisce l'implementazione dell'host di una rappresentazione di un evento di reimpostazione manuale.</span><span class="sxs-lookup"><span data-stu-id="a2299-103">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a2299-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="a2299-104">Methods</span></span>  
  
|<span data-ttu-id="a2299-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="a2299-105">Method</span></span>|<span data-ttu-id="a2299-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a2299-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a2299-107">Reset (metodo)</span><span class="sxs-lookup"><span data-stu-id="a2299-107">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)|<span data-ttu-id="a2299-108">Reimposta corrente `IHostManualEvent` istanza da uno stato non segnalato.</span><span class="sxs-lookup"><span data-stu-id="a2299-108">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="a2299-109">Set (metodo)</span><span class="sxs-lookup"><span data-stu-id="a2299-109">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-set-method.md)|<span data-ttu-id="a2299-110">Imposta l'oggetto corrente `IHostManualEvent` istanza sullo stato segnalato.</span><span class="sxs-lookup"><span data-stu-id="a2299-110">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="a2299-111">Wait (metodo)</span><span class="sxs-lookup"><span data-stu-id="a2299-111">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-wait-method.md)|<span data-ttu-id="a2299-112">Fa sì che l'oggetto corrente `IHostManualEvent` in attesa fino a quando non è di proprietà istanza o un determinato periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="a2299-112">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a2299-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a2299-113">Requirements</span></span>  
 <span data-ttu-id="a2299-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2299-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2299-115">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="a2299-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a2299-116">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a2299-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a2299-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2299-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2299-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2299-118">See Also</span></span>  
 [<span data-ttu-id="a2299-119">ICLRSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="a2299-119">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="a2299-120">IHostAutoEvent (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="a2299-120">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="a2299-121">IHostSemaphore (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="a2299-121">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="a2299-122">IHostSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="a2299-122">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="a2299-123">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="a2299-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

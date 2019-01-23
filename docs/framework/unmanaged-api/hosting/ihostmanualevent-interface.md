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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb09422872a0d9565be286c25ca1b28d1c45e08f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54501698"
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="d78b1-102">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="d78b1-102">IHostManualEvent Interface</span></span>
<span data-ttu-id="d78b1-103">Fornisce l'implementazione dell'host di una rappresentazione di un evento di reimpostazione manuale.</span><span class="sxs-lookup"><span data-stu-id="d78b1-103">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d78b1-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="d78b1-104">Methods</span></span>  
  
|<span data-ttu-id="d78b1-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="d78b1-105">Method</span></span>|<span data-ttu-id="d78b1-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d78b1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d78b1-107">Metodo Reset</span><span class="sxs-lookup"><span data-stu-id="d78b1-107">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)|<span data-ttu-id="d78b1-108">Reimposta corrente `IHostManualEvent` istanza da uno stato non segnalato.</span><span class="sxs-lookup"><span data-stu-id="d78b1-108">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="d78b1-109">Metodo Set</span><span class="sxs-lookup"><span data-stu-id="d78b1-109">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-set-method.md)|<span data-ttu-id="d78b1-110">Imposta l'oggetto corrente `IHostManualEvent` istanza da uno stato segnalato.</span><span class="sxs-lookup"><span data-stu-id="d78b1-110">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="d78b1-111">Metodo Wait</span><span class="sxs-lookup"><span data-stu-id="d78b1-111">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-wait-method.md)|<span data-ttu-id="d78b1-112">Fa sì che l'oggetto corrente `IHostManualEvent` istanza in attesa fino a quando non è di proprietà o un determinato periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="d78b1-112">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d78b1-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d78b1-113">Requirements</span></span>  
 <span data-ttu-id="d78b1-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d78b1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d78b1-115">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d78b1-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d78b1-116">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d78b1-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d78b1-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d78b1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d78b1-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d78b1-118">See also</span></span>
- [<span data-ttu-id="d78b1-119">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="d78b1-119">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="d78b1-120">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="d78b1-120">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="d78b1-121">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="d78b1-121">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="d78b1-122">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="d78b1-122">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="d78b1-123">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="d78b1-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

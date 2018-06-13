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
ms.openlocfilehash: 53aaf4c23861666962e5567a6cf9eb9fffc6292f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438756"
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="f8e76-102">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="f8e76-102">IHostManualEvent Interface</span></span>
<span data-ttu-id="f8e76-103">Fornisce l'implementazione dell'host di una rappresentazione di un evento di reimpostazione manuale.</span><span class="sxs-lookup"><span data-stu-id="f8e76-103">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f8e76-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="f8e76-104">Methods</span></span>  
  
|<span data-ttu-id="f8e76-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="f8e76-105">Method</span></span>|<span data-ttu-id="f8e76-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8e76-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f8e76-107">Metodo Reset</span><span class="sxs-lookup"><span data-stu-id="f8e76-107">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)|<span data-ttu-id="f8e76-108">Reimposta corrente `IHostManualEvent` istanza da uno stato non segnalato.</span><span class="sxs-lookup"><span data-stu-id="f8e76-108">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="f8e76-109">Metodo Set</span><span class="sxs-lookup"><span data-stu-id="f8e76-109">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-set-method.md)|<span data-ttu-id="f8e76-110">Imposta l'oggetto corrente `IHostManualEvent` istanza sullo stato segnalato.</span><span class="sxs-lookup"><span data-stu-id="f8e76-110">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="f8e76-111">Metodo Wait</span><span class="sxs-lookup"><span data-stu-id="f8e76-111">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-wait-method.md)|<span data-ttu-id="f8e76-112">Fa sì che l'oggetto corrente `IHostManualEvent` in attesa fino a quando non è di proprietà istanza o un determinato periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="f8e76-112">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f8e76-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f8e76-113">Requirements</span></span>  
 <span data-ttu-id="f8e76-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8e76-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8e76-115">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="f8e76-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f8e76-116">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="f8e76-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f8e76-117">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8e76-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8e76-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8e76-118">See Also</span></span>  
 [<span data-ttu-id="f8e76-119">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="f8e76-119">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="f8e76-120">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="f8e76-120">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="f8e76-121">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="f8e76-121">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="f8e76-122">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="f8e76-122">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="f8e76-123">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="f8e76-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

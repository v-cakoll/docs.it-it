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
ms.openlocfilehash: 7c46f00063cdf9281a5f1080594e8d6dbc6c101e
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804587"
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="31034-102">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="31034-102">IHostManualEvent Interface</span></span>
<span data-ttu-id="31034-103">Fornisce l'implementazione dell'host di una rappresentazione di un evento di reimpostazione manuale.</span><span class="sxs-lookup"><span data-stu-id="31034-103">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="31034-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="31034-104">Methods</span></span>  
  
|<span data-ttu-id="31034-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="31034-105">Method</span></span>|<span data-ttu-id="31034-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="31034-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="31034-107">Metodo Reset</span><span class="sxs-lookup"><span data-stu-id="31034-107">Reset Method</span></span>](ihostmanualevent-reset-method.md)|<span data-ttu-id="31034-108">Reimposta l'istanza corrente `IHostManualEvent` su uno stato non segnalato.</span><span class="sxs-lookup"><span data-stu-id="31034-108">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="31034-109">Metodo Set</span><span class="sxs-lookup"><span data-stu-id="31034-109">Set Method</span></span>](ihostmanualevent-set-method.md)|<span data-ttu-id="31034-110">Imposta l' `IHostManualEvent` istanza corrente su uno stato segnalato.</span><span class="sxs-lookup"><span data-stu-id="31034-110">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="31034-111">Metodo Wait</span><span class="sxs-lookup"><span data-stu-id="31034-111">Wait Method</span></span>](ihostmanualevent-wait-method.md)|<span data-ttu-id="31034-112">Fa `IHostManualEvent` in modo che l'istanza corrente attenda fino a quando non è di proprietà o che trascorre un intervallo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="31034-112">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="31034-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="31034-113">Requirements</span></span>  
 <span data-ttu-id="31034-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31034-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31034-115">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="31034-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="31034-116">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="31034-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="31034-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31034-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31034-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31034-118">See also</span></span>

- [<span data-ttu-id="31034-119">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="31034-119">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="31034-120">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="31034-120">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="31034-121">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="31034-121">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="31034-122">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="31034-122">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="31034-123">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="31034-123">Hosting Interfaces</span></span>](hosting-interfaces.md)

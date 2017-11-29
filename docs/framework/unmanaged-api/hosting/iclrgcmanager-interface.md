---
title: Interfaccia ICLRGCManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRGCManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRGCManager
helpviewer_keywords: ICLRGCManager interface [.NET Framework hosting]
ms.assetid: fb511c9b-3fe4-41b0-822a-6ba4a079d1f5
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7215ce1423e8541b23daae7b9e051ade6e25f1b7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrgcmanager-interface"></a><span data-ttu-id="3e4c6-102">Interfaccia ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="3e4c6-102">ICLRGCManager Interface</span></span>
<span data-ttu-id="3e4c6-103">Fornisce metodi che consentono a un host di interagire con sistema di garbage collection di common language runtime.</span><span class="sxs-lookup"><span data-stu-id="3e4c6-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3e4c6-104">A partire dal [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], è possibile utilizzare il [iclrgcmanager2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) per impostare le dimensioni di un segmento di garbage collection e la dimensione massima della generazione del sistema di garbage collection 0 su valori di maggiore (metodo) più il `DWORD` limite imposto dal [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="3e4c6-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can use the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3e4c6-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="3e4c6-105">Methods</span></span>  
  
|<span data-ttu-id="3e4c6-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="3e4c6-106">Method</span></span>|<span data-ttu-id="3e4c6-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3e4c6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3e4c6-108">Collect (metodo)</span><span class="sxs-lookup"><span data-stu-id="3e4c6-108">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-collect-method.md)|<span data-ttu-id="3e4c6-109">Forza un'operazione di garbage collection per la generazione specificata.</span><span class="sxs-lookup"><span data-stu-id="3e4c6-109">Forces a garbage collection for the specified generation.</span></span>|  
|[<span data-ttu-id="3e4c6-110">GetStats (metodo)</span><span class="sxs-lookup"><span data-stu-id="3e4c6-110">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md)|<span data-ttu-id="3e4c6-111">Ottiene un set di statistiche sul sistema di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="3e4c6-111">Gets a set of current statistics about the garbage collection system.</span></span>|  
|[<span data-ttu-id="3e4c6-112">SetGCStartupLimits (metodo)</span><span class="sxs-lookup"><span data-stu-id="3e4c6-112">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)|<span data-ttu-id="3e4c6-113">Imposta le dimensioni di un segmento di garbage collection e la dimensione massima della generazione del sistema di garbage collection 0.</span><span class="sxs-lookup"><span data-stu-id="3e4c6-113">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e4c6-114">Note</span><span class="sxs-lookup"><span data-stu-id="3e4c6-114">Remarks</span></span>  
 <span data-ttu-id="3e4c6-115">Common language runtime (CLR) implementa il meccanismo di garbage collection con gestito <xref:System.GC> tipo.</span><span class="sxs-lookup"><span data-stu-id="3e4c6-115">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="3e4c6-116">Per ulteriori informazioni sul sistema di garbage collection, vedere [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="3e4c6-116">For more information about the garbage collection system, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e4c6-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3e4c6-117">Requirements</span></span>  
 <span data-ttu-id="3e4c6-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e4c6-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e4c6-119">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="3e4c6-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3e4c6-120">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3e4c6-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3e4c6-121">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e4c6-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e4c6-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e4c6-122">See Also</span></span>  
 [<span data-ttu-id="3e4c6-123">Gestione automatica della memoria</span><span class="sxs-lookup"><span data-stu-id="3e4c6-123">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="3e4c6-124">COR_GC_STATS (struttura)</span><span class="sxs-lookup"><span data-stu-id="3e4c6-124">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [<span data-ttu-id="3e4c6-125">ICLRControl (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="3e4c6-125">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="3e4c6-126">Interfacce di Hosting CLR</span><span class="sxs-lookup"><span data-stu-id="3e4c6-126">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="3e4c6-127">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="3e4c6-127">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="3e4c6-128">Hosting</span><span class="sxs-lookup"><span data-stu-id="3e4c6-128">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)

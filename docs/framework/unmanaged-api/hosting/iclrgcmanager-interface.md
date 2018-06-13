---
title: Interfaccia ICLRGCManager
ms.date: 03/30/2017
api_name:
- ICLRGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager
helpviewer_keywords:
- ICLRGCManager interface [.NET Framework hosting]
ms.assetid: fb511c9b-3fe4-41b0-822a-6ba4a079d1f5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 045b924033630ea98d5a532a62f1037a5972df90
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433924"
---
# <a name="iclrgcmanager-interface"></a><span data-ttu-id="5bbd0-102">Interfaccia ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="5bbd0-102">ICLRGCManager Interface</span></span>
<span data-ttu-id="5bbd0-103">Fornisce metodi che consentono a un host di interagire con sistema di garbage collection di common language runtime.</span><span class="sxs-lookup"><span data-stu-id="5bbd0-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5bbd0-104">A partire dal [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], è possibile utilizzare il [iclrgcmanager2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) per impostare le dimensioni di un segmento di garbage collection e la dimensione massima della generazione del sistema di garbage collection 0 su valori di maggiore (metodo) più il `DWORD` limite imposto dal [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="5bbd0-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can use the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5bbd0-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="5bbd0-105">Methods</span></span>  
  
|<span data-ttu-id="5bbd0-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="5bbd0-106">Method</span></span>|<span data-ttu-id="5bbd0-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5bbd0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5bbd0-108">Metodo Collect</span><span class="sxs-lookup"><span data-stu-id="5bbd0-108">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-collect-method.md)|<span data-ttu-id="5bbd0-109">Forza un'operazione di garbage collection per la generazione specificata.</span><span class="sxs-lookup"><span data-stu-id="5bbd0-109">Forces a garbage collection for the specified generation.</span></span>|  
|[<span data-ttu-id="5bbd0-110">Metodo GetStats</span><span class="sxs-lookup"><span data-stu-id="5bbd0-110">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md)|<span data-ttu-id="5bbd0-111">Ottiene un set di statistiche sul sistema di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="5bbd0-111">Gets a set of current statistics about the garbage collection system.</span></span>|  
|[<span data-ttu-id="5bbd0-112">Metodo SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="5bbd0-112">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)|<span data-ttu-id="5bbd0-113">Imposta le dimensioni di un segmento di garbage collection e la dimensione massima della generazione del sistema di garbage collection 0.</span><span class="sxs-lookup"><span data-stu-id="5bbd0-113">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5bbd0-114">Note</span><span class="sxs-lookup"><span data-stu-id="5bbd0-114">Remarks</span></span>  
 <span data-ttu-id="5bbd0-115">Common language runtime (CLR) implementa il meccanismo di garbage collection con gestito <xref:System.GC> tipo.</span><span class="sxs-lookup"><span data-stu-id="5bbd0-115">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="5bbd0-116">Per ulteriori informazioni sul sistema di garbage collection, vedere [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="5bbd0-116">For more information about the garbage collection system, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bbd0-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5bbd0-117">Requirements</span></span>  
 <span data-ttu-id="5bbd0-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5bbd0-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bbd0-119">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="5bbd0-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5bbd0-120">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="5bbd0-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5bbd0-121">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bbd0-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bbd0-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5bbd0-122">See Also</span></span>  
 [<span data-ttu-id="5bbd0-123">Gestione automatica della memoria</span><span class="sxs-lookup"><span data-stu-id="5bbd0-123">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="5bbd0-124">Struttura COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="5bbd0-124">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [<span data-ttu-id="5bbd0-125">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="5bbd0-125">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="5bbd0-126">Interfacce di hosting CLR</span><span class="sxs-lookup"><span data-stu-id="5bbd0-126">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="5bbd0-127">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="5bbd0-127">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="5bbd0-128">Hosting</span><span class="sxs-lookup"><span data-stu-id="5bbd0-128">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)

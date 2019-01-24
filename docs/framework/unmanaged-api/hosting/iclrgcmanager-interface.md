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
ms.openlocfilehash: 27899994a048c7000746a2e92516776fd23f8e2e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624392"
---
# <a name="iclrgcmanager-interface"></a><span data-ttu-id="aa351-102">Interfaccia ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="aa351-102">ICLRGCManager Interface</span></span>
<span data-ttu-id="aa351-103">Fornisce metodi che consentono a un host interagire con il sistema di common language runtime garbage collection.</span><span class="sxs-lookup"><span data-stu-id="aa351-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa351-104">Inizia con la [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], è possibile usare il [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) metodo per impostare le dimensioni di un segmento di garbage collection e le dimensioni massime della generazione del sistema di garbage collection 0 sui valori superiori rispetto al `DWORD` limite imposto per la [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="aa351-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can use the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="aa351-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="aa351-105">Methods</span></span>  
  
|<span data-ttu-id="aa351-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="aa351-106">Method</span></span>|<span data-ttu-id="aa351-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aa351-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="aa351-108">Metodo Collect</span><span class="sxs-lookup"><span data-stu-id="aa351-108">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-collect-method.md)|<span data-ttu-id="aa351-109">Forza un'operazione di garbage collection per la generazione specificata.</span><span class="sxs-lookup"><span data-stu-id="aa351-109">Forces a garbage collection for the specified generation.</span></span>|  
|[<span data-ttu-id="aa351-110">Metodo GetStats</span><span class="sxs-lookup"><span data-stu-id="aa351-110">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md)|<span data-ttu-id="aa351-111">Ottiene un set di statistiche correnti sul sistema di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="aa351-111">Gets a set of current statistics about the garbage collection system.</span></span>|  
|[<span data-ttu-id="aa351-112">Metodo SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="aa351-112">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)|<span data-ttu-id="aa351-113">Imposta le dimensioni di un segmento di garbage collection e le dimensioni massime della generazione del sistema di garbage collection 0.</span><span class="sxs-lookup"><span data-stu-id="aa351-113">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa351-114">Note</span><span class="sxs-lookup"><span data-stu-id="aa351-114">Remarks</span></span>  
 <span data-ttu-id="aa351-115">Common language runtime (CLR) implementa il meccanismo di garbage collection con managed <xref:System.GC> tipo.</span><span class="sxs-lookup"><span data-stu-id="aa351-115">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="aa351-116">Per altre informazioni sul sistema di garbage collection, vedere [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="aa351-116">For more information about the garbage collection system, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa351-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="aa351-117">Requirements</span></span>  
 <span data-ttu-id="aa351-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa351-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa351-119">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="aa351-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aa351-120">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="aa351-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aa351-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa351-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa351-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa351-122">See also</span></span>
- [<span data-ttu-id="aa351-123">Gestione automatica della memoria</span><span class="sxs-lookup"><span data-stu-id="aa351-123">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="aa351-124">Struttura COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="aa351-124">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="aa351-125">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="aa351-125">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="aa351-126">Interfacce di hosting CLR</span><span class="sxs-lookup"><span data-stu-id="aa351-126">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="aa351-127">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="aa351-127">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="aa351-128">Hosting</span><span class="sxs-lookup"><span data-stu-id="aa351-128">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)

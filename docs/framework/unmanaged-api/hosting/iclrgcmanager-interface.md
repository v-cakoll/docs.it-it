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
ms.openlocfilehash: b9519f7c2df5cf078bac6be038275527d7741edb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700839"
---
# <a name="iclrgcmanager-interface"></a><span data-ttu-id="1debf-102">Interfaccia ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="1debf-102">ICLRGCManager Interface</span></span>
<span data-ttu-id="1debf-103">Fornisce metodi che consentono a un host interagire con il sistema di common language runtime garbage collection.</span><span class="sxs-lookup"><span data-stu-id="1debf-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1debf-104">Inizia con la [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], è possibile usare il [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) metodo per impostare le dimensioni di un segmento di garbage collection e le dimensioni massime della generazione del sistema di garbage collection 0 sui valori superiori rispetto al `DWORD` limite imposto per la [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="1debf-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can use the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1debf-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="1debf-105">Methods</span></span>  
  
|<span data-ttu-id="1debf-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="1debf-106">Method</span></span>|<span data-ttu-id="1debf-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1debf-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1debf-108">Metodo Collect</span><span class="sxs-lookup"><span data-stu-id="1debf-108">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-collect-method.md)|<span data-ttu-id="1debf-109">Forza un'operazione di garbage collection per la generazione specificata.</span><span class="sxs-lookup"><span data-stu-id="1debf-109">Forces a garbage collection for the specified generation.</span></span>|  
|[<span data-ttu-id="1debf-110">Metodo GetStats</span><span class="sxs-lookup"><span data-stu-id="1debf-110">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md)|<span data-ttu-id="1debf-111">Ottiene un set di statistiche correnti sul sistema di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="1debf-111">Gets a set of current statistics about the garbage collection system.</span></span>|  
|[<span data-ttu-id="1debf-112">Metodo SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="1debf-112">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)|<span data-ttu-id="1debf-113">Imposta le dimensioni di un segmento di garbage collection e le dimensioni massime della generazione del sistema di garbage collection 0.</span><span class="sxs-lookup"><span data-stu-id="1debf-113">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1debf-114">Note</span><span class="sxs-lookup"><span data-stu-id="1debf-114">Remarks</span></span>  
 <span data-ttu-id="1debf-115">Common language runtime (CLR) implementa il meccanismo di garbage collection con managed <xref:System.GC> tipo.</span><span class="sxs-lookup"><span data-stu-id="1debf-115">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="1debf-116">Per altre informazioni sul sistema di garbage collection, vedere [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="1debf-116">For more information about the garbage collection system, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1debf-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1debf-117">Requirements</span></span>  
 <span data-ttu-id="1debf-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1debf-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1debf-119">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1debf-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1debf-120">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="1debf-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1debf-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1debf-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1debf-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1debf-122">See also</span></span>

- [<span data-ttu-id="1debf-123">Gestione automatica della memoria</span><span class="sxs-lookup"><span data-stu-id="1debf-123">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="1debf-124">Struttura COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="1debf-124">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="1debf-125">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="1debf-125">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="1debf-126">Interfacce di hosting CLR</span><span class="sxs-lookup"><span data-stu-id="1debf-126">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="1debf-127">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="1debf-127">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="1debf-128">Hosting</span><span class="sxs-lookup"><span data-stu-id="1debf-128">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)

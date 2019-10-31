---
title: Interfaccia ICLRGCManager2
ms.date: 03/30/2017
api_name:
- ICLRGCManager2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager2
helpviewer_keywords:
- ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 4b5ffd7b-9ad7-41cd-9bba-34030ae3da7e
topic_type:
- apiref
ms.openlocfilehash: 72ffd7b47795ee8e46f8fbff07559133843793e6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141154"
---
# <a name="iclrgcmanager2-interface"></a><span data-ttu-id="d7742-102">Interfaccia ICLRGCManager2</span><span class="sxs-lookup"><span data-stu-id="d7742-102">ICLRGCManager2 Interface</span></span>
<span data-ttu-id="d7742-103">Fornisce metodi che consentono a un host di interagire con il sistema di Garbage Collection del Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="d7742-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d7742-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="d7742-104">Methods</span></span>  
  
|<span data-ttu-id="d7742-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="d7742-105">Method</span></span>|<span data-ttu-id="d7742-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d7742-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d7742-107">Metodo SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="d7742-107">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)|<span data-ttu-id="d7742-108">Imposta la dimensione di un segmento di Garbage Collection e la dimensione massima della generazione 0 del sistema Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="d7742-108">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span> <span data-ttu-id="d7742-109">Abilita la generazione 0 e le dimensioni dei segmenti maggiori di `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="d7742-109">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7742-110">Note</span><span class="sxs-lookup"><span data-stu-id="d7742-110">Remarks</span></span>  
 <span data-ttu-id="d7742-111">Questa interfaccia eredita dall' [Interfaccia ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="d7742-111">This interface inherits from the [ICLRGCManager Interface](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span></span>  
  
 <span data-ttu-id="d7742-112">Il Common Language Runtime (CLR) implementa il meccanismo Garbage Collection con il tipo di <xref:System.GC> gestito.</span><span class="sxs-lookup"><span data-stu-id="d7742-112">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="d7742-113">Per ulteriori informazioni sul sistema di Garbage Collection, vedere [Garbage Collection](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="d7742-113">For more information about the garbage collection system, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7742-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d7742-114">Requirements</span></span>  
 <span data-ttu-id="d7742-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7742-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7742-116">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d7742-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d7742-117">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d7742-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d7742-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7742-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7742-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7742-119">See also</span></span>

- [<span data-ttu-id="d7742-120">Gestione automatica della memoria</span><span class="sxs-lookup"><span data-stu-id="d7742-120">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="d7742-121">Struttura COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="d7742-121">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="d7742-122">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="d7742-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="d7742-123">Interfacce di hosting CLR aggiunte in .NET Framework 4 e 4.5</span><span class="sxs-lookup"><span data-stu-id="d7742-123">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="d7742-124">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="d7742-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="d7742-125">Hosting</span><span class="sxs-lookup"><span data-stu-id="d7742-125">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)

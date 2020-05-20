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
ms.openlocfilehash: 0f3ecc0d497eaee937647df47ba0956335a2fe41
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703952"
---
# <a name="iclrgcmanager2-interface"></a><span data-ttu-id="888a9-102">Interfaccia ICLRGCManager2</span><span class="sxs-lookup"><span data-stu-id="888a9-102">ICLRGCManager2 Interface</span></span>
<span data-ttu-id="888a9-103">Fornisce metodi che consentono a un host di interagire con il sistema di Garbage Collection del Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="888a9-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="888a9-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="888a9-104">Methods</span></span>  
  
|<span data-ttu-id="888a9-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="888a9-105">Method</span></span>|<span data-ttu-id="888a9-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="888a9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="888a9-107">Metodo SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="888a9-107">SetGCStartupLimitsEx Method</span></span>](iclrgcmanager2-setgcstartuplimitsex-method.md)|<span data-ttu-id="888a9-108">Imposta la dimensione di un segmento di Garbage Collection e la dimensione massima della generazione 0 del sistema Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="888a9-108">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span> <span data-ttu-id="888a9-109">Abilita la generazione 0 e le dimensioni dei segmenti maggiori di `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="888a9-109">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="888a9-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="888a9-110">Remarks</span></span>  
 <span data-ttu-id="888a9-111">Questa interfaccia eredita dall' [Interfaccia ICLRGCManager](iclrgcmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="888a9-111">This interface inherits from the [ICLRGCManager Interface](iclrgcmanager-interface.md).</span></span>  
  
 <span data-ttu-id="888a9-112">Il Common Language Runtime (CLR) implementa il meccanismo Garbage Collection con il <xref:System.GC> tipo gestito.</span><span class="sxs-lookup"><span data-stu-id="888a9-112">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="888a9-113">Per ulteriori informazioni sul sistema di Garbage Collection, vedere [Garbage Collection](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="888a9-113">For more information about the garbage collection system, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="888a9-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="888a9-114">Requirements</span></span>  
 <span data-ttu-id="888a9-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="888a9-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="888a9-116">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="888a9-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="888a9-117">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="888a9-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="888a9-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="888a9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="888a9-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="888a9-119">See also</span></span>

- [<span data-ttu-id="888a9-120">Gestione automatica della memoria</span><span class="sxs-lookup"><span data-stu-id="888a9-120">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="888a9-121">Struttura COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="888a9-121">COR_GC_STATS Structure</span></span>](cor-gc-stats-structure.md)
- [<span data-ttu-id="888a9-122">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="888a9-122">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="888a9-123">Interfacce di hosting CLR aggiunte in .NET Framework 4 e 4.5</span><span class="sxs-lookup"><span data-stu-id="888a9-123">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="888a9-124">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="888a9-124">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="888a9-125">Hosting</span><span class="sxs-lookup"><span data-stu-id="888a9-125">Hosting</span></span>](index.md)

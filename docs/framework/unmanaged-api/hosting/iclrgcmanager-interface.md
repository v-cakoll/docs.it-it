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
ms.openlocfilehash: f878e2f1f86bc42c0ff5abada8d7df4feb9ed228
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504191"
---
# <a name="iclrgcmanager-interface"></a><span data-ttu-id="4c31c-102">Interfaccia ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="4c31c-102">ICLRGCManager Interface</span></span>
<span data-ttu-id="4c31c-103">Fornisce metodi che consentono a un host di interagire con il sistema di Garbage Collection del Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="4c31c-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4c31c-104">A partire da .NET Framework 4,5, è possibile usare il metodo [ICLRGCManager2:: SetGCStartupLimitsEx](iclrgcmanager2-setgcstartuplimitsex-method.md) per impostare le dimensioni di un segmento di Garbage Collection e le dimensioni massime della generazione 0 del sistema di Garbage Collection su valori maggiori del `DWORD` limite imposto dal metodo [SetGCStartupLimits](iclrgcmanager-setgcstartuplimits-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4c31c-104">Starting with the .NET Framework 4.5, you can use the [ICLRGCManager2::SetGCStartupLimitsEx](iclrgcmanager2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](iclrgcmanager-setgcstartuplimits-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4c31c-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="4c31c-105">Methods</span></span>  
  
|<span data-ttu-id="4c31c-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="4c31c-106">Method</span></span>|<span data-ttu-id="4c31c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4c31c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4c31c-108">Metodo Collect</span><span class="sxs-lookup"><span data-stu-id="4c31c-108">Collect Method</span></span>](iclrgcmanager-collect-method.md)|<span data-ttu-id="4c31c-109">Impone un Garbage Collection per la generazione specificata.</span><span class="sxs-lookup"><span data-stu-id="4c31c-109">Forces a garbage collection for the specified generation.</span></span>|  
|[<span data-ttu-id="4c31c-110">Metodo GetStats</span><span class="sxs-lookup"><span data-stu-id="4c31c-110">GetStats Method</span></span>](iclrgcmanager-getstats-method.md)|<span data-ttu-id="4c31c-111">Ottiene un set di statistiche correnti sul sistema di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4c31c-111">Gets a set of current statistics about the garbage collection system.</span></span>|  
|[<span data-ttu-id="4c31c-112">Metodo SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="4c31c-112">SetGCStartupLimits Method</span></span>](iclrgcmanager-setgcstartuplimits-method.md)|<span data-ttu-id="4c31c-113">Imposta la dimensione di un segmento di Garbage Collection e la dimensione massima della generazione 0 del sistema Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4c31c-113">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c31c-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4c31c-114">Remarks</span></span>  
 <span data-ttu-id="4c31c-115">Il Common Language Runtime (CLR) implementa il meccanismo Garbage Collection con il <xref:System.GC> tipo gestito.</span><span class="sxs-lookup"><span data-stu-id="4c31c-115">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="4c31c-116">Per ulteriori informazioni sul sistema di Garbage Collection, vedere [Garbage Collection](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="4c31c-116">For more information about the garbage collection system, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c31c-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4c31c-117">Requirements</span></span>  
 <span data-ttu-id="4c31c-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c31c-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c31c-119">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4c31c-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4c31c-120">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4c31c-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4c31c-121">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c31c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c31c-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c31c-122">See also</span></span>

- [<span data-ttu-id="4c31c-123">Gestione automatica della memoria</span><span class="sxs-lookup"><span data-stu-id="4c31c-123">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="4c31c-124">Struttura COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="4c31c-124">COR_GC_STATS Structure</span></span>](cor-gc-stats-structure.md)
- [<span data-ttu-id="4c31c-125">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="4c31c-125">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="4c31c-126">Interfacce di hosting CLR</span><span class="sxs-lookup"><span data-stu-id="4c31c-126">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="4c31c-127">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="4c31c-127">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="4c31c-128">Hosting</span><span class="sxs-lookup"><span data-stu-id="4c31c-128">Hosting</span></span>](index.md)

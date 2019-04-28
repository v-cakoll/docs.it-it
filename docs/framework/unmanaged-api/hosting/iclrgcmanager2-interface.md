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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a89a7ef34418163d790fd055de681c1cdf989e57
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700425"
---
# <a name="iclrgcmanager2-interface"></a><span data-ttu-id="28add-102">Interfaccia ICLRGCManager2</span><span class="sxs-lookup"><span data-stu-id="28add-102">ICLRGCManager2 Interface</span></span>
<span data-ttu-id="28add-103">Fornisce metodi che consentono a un host interagire con il sistema di common language runtime garbage collection.</span><span class="sxs-lookup"><span data-stu-id="28add-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="28add-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="28add-104">Methods</span></span>  
  
|<span data-ttu-id="28add-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="28add-105">Method</span></span>|<span data-ttu-id="28add-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="28add-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="28add-107">Metodo SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="28add-107">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)|<span data-ttu-id="28add-108">Imposta le dimensioni di un segmento di garbage collection e le dimensioni massime della generazione del sistema di garbage collection 0.</span><span class="sxs-lookup"><span data-stu-id="28add-108">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span> <span data-ttu-id="28add-109">Abilita generazione 0 e dimensioni del segmento superiori a `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="28add-109">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28add-110">Note</span><span class="sxs-lookup"><span data-stu-id="28add-110">Remarks</span></span>  
 <span data-ttu-id="28add-111">Questa interfaccia eredita dal [interfaccia ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="28add-111">This interface inherits from the [ICLRGCManager Interface](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span></span>  
  
 <span data-ttu-id="28add-112">Common language runtime (CLR) implementa il meccanismo di garbage collection con managed <xref:System.GC> tipo.</span><span class="sxs-lookup"><span data-stu-id="28add-112">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="28add-113">Per altre informazioni sul sistema di garbage collection, vedere [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="28add-113">For more information about the garbage collection system, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28add-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="28add-114">Requirements</span></span>  
 <span data-ttu-id="28add-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28add-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28add-116">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="28add-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="28add-117">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="28add-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="28add-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28add-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28add-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28add-119">See also</span></span>

- [<span data-ttu-id="28add-120">Gestione automatica della memoria</span><span class="sxs-lookup"><span data-stu-id="28add-120">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="28add-121">Struttura COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="28add-121">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="28add-122">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="28add-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="28add-123">Interfacce di hosting CLR aggiunte in .NET Framework 4 e 4.5</span><span class="sxs-lookup"><span data-stu-id="28add-123">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="28add-124">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="28add-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="28add-125">Hosting</span><span class="sxs-lookup"><span data-stu-id="28add-125">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)

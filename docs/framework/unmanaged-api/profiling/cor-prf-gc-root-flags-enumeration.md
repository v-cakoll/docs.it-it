---
title: Enumerazione COR_PRF_GC_ROOT_FLAGS
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_ROOT_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_ROOT_FLAGS
helpviewer_keywords:
- COR_PRF_GC_ROOT_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 4611ee6f-0f05-4d84-91e1-e83d5e7dd7e4
topic_type:
- apiref
ms.openlocfilehash: bbc163c71b47e6fee0db89284d6e3fd27e882768
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500887"
---
# <a name="cor_prf_gc_root_flags-enumeration"></a><span data-ttu-id="96ebb-102">Enumerazione COR_PRF_GC_ROOT_FLAGS</span><span class="sxs-lookup"><span data-stu-id="96ebb-102">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>
<span data-ttu-id="96ebb-103">Indica una proprietà di un Garbage Collection radice.</span><span class="sxs-lookup"><span data-stu-id="96ebb-103">Indicates a property of a garbage collection root.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96ebb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="96ebb-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="96ebb-105">Membri</span><span class="sxs-lookup"><span data-stu-id="96ebb-105">Members</span></span>  
  
|<span data-ttu-id="96ebb-106">Membro</span><span class="sxs-lookup"><span data-stu-id="96ebb-106">Member</span></span>|<span data-ttu-id="96ebb-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="96ebb-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|<span data-ttu-id="96ebb-108">La radice impedisce a un Garbage Collection di migrare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="96ebb-108">The root prevents a garbage collection from moving the object.</span></span>|  
|`COR_PRF_GC_ROOT_WEAKREF`|<span data-ttu-id="96ebb-109">La radice non impedisce Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="96ebb-109">The root does not prevent garbage collection.</span></span>|  
|`COR_PRF_GC_ROOT_INTERIOR`|<span data-ttu-id="96ebb-110">La radice fa riferimento a un campo dell'oggetto anziché all'oggetto stesso.</span><span class="sxs-lookup"><span data-stu-id="96ebb-110">The root refers to a field of the object rather than the object itself.</span></span>|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|<span data-ttu-id="96ebb-111">La radice impedisce Garbage Collection se il conteggio dei riferimenti dell'oggetto è un determinato valore.</span><span class="sxs-lookup"><span data-stu-id="96ebb-111">The root prevents garbage collection if the reference count of the object is a certain value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96ebb-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="96ebb-112">Remarks</span></span>  
 <span data-ttu-id="96ebb-113">`COR_PRF_GC_ROOT_FLAGS`è una maschera di maschera che fornisce informazioni aggiuntive sulle radici speciali.</span><span class="sxs-lookup"><span data-stu-id="96ebb-113">`COR_PRF_GC_ROOT_FLAGS` is a bitmask that provides additional information about special roots.</span></span> <span data-ttu-id="96ebb-114">Tuttavia, non tutte le radici sono particolari.</span><span class="sxs-lookup"><span data-stu-id="96ebb-114">However, not all roots are special.</span></span> <span data-ttu-id="96ebb-115">Alcune radici, ad esempio, non sono riferimenti vulnerabili, puntatori interni, aggiunti o conteggiati come riferimenti.</span><span class="sxs-lookup"><span data-stu-id="96ebb-115">For example, some roots are not weak references, interior pointers, pinned, or reference-counted.</span></span> <span data-ttu-id="96ebb-116">Per tali radici, non sono presenti flag da inserire.</span><span class="sxs-lookup"><span data-stu-id="96ebb-116">For such roots, there are no flags to convey.</span></span> <span data-ttu-id="96ebb-117">Pertanto, i metodi che utilizzano questa enumerazione, ad esempio il metodo [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) , inviano 0 per la maschera di maschera dei flag, che indica che tutti i flag sono disattivati.</span><span class="sxs-lookup"><span data-stu-id="96ebb-117">Therefore, methods that use this enumeration, such as the [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) method, send 0 for the flags bitmask, indicating that all flags are turned off.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96ebb-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="96ebb-118">Requirements</span></span>  
 <span data-ttu-id="96ebb-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96ebb-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96ebb-120">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="96ebb-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="96ebb-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96ebb-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96ebb-122">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96ebb-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96ebb-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96ebb-123">See also</span></span>

- [<span data-ttu-id="96ebb-124">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="96ebb-124">Profiling Enumerations</span></span>](profiling-enumerations.md)

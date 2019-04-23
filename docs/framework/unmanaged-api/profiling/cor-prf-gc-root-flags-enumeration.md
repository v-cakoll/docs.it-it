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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 263c22a07f363c2752afb50779515de043976e93
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207708"
---
# <a name="corprfgcrootflags-enumeration"></a><span data-ttu-id="0e19c-102">Enumerazione COR_PRF_GC_ROOT_FLAGS</span><span class="sxs-lookup"><span data-stu-id="0e19c-102">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>
<span data-ttu-id="0e19c-103">Indica una proprietà di una radice di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="0e19c-103">Indicates a property of a garbage collection root.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e19c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0e19c-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="0e19c-105">Membri</span><span class="sxs-lookup"><span data-stu-id="0e19c-105">Members</span></span>  
  
|<span data-ttu-id="0e19c-106">Member</span><span class="sxs-lookup"><span data-stu-id="0e19c-106">Member</span></span>|<span data-ttu-id="0e19c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0e19c-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|<span data-ttu-id="0e19c-108">La radice impedisce un'operazione di garbage collection di spostare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="0e19c-108">The root prevents a garbage collection from moving the object.</span></span>|  
|`COR_PRF_GC_ROOT_WEAKREF`|<span data-ttu-id="0e19c-109">La radice non impedisce l'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="0e19c-109">The root does not prevent garbage collection.</span></span>|  
|`COR_PRF_GC_ROOT_INTERIOR`|<span data-ttu-id="0e19c-110">La radice fa riferimento a un campo dell'oggetto anziché l'oggetto stesso.</span><span class="sxs-lookup"><span data-stu-id="0e19c-110">The root refers to a field of the object rather than the object itself.</span></span>|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|<span data-ttu-id="0e19c-111">Radice impedisce l'operazione di garbage collection se il conteggio dei riferimenti dell'oggetto è un determinato valore.</span><span class="sxs-lookup"><span data-stu-id="0e19c-111">The root prevents garbage collection if the reference count of the object is a certain value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e19c-112">Note</span><span class="sxs-lookup"><span data-stu-id="0e19c-112">Remarks</span></span>  
 <span data-ttu-id="0e19c-113">`COR_PRF_GC_ROOT_FLAGS` è una maschera di bit che fornisce informazioni aggiuntive sulle radici speciali.</span><span class="sxs-lookup"><span data-stu-id="0e19c-113">`COR_PRF_GC_ROOT_FLAGS` is a bitmask that provides additional information about special roots.</span></span> <span data-ttu-id="0e19c-114">Tuttavia, non tutte le radici sono speciali.</span><span class="sxs-lookup"><span data-stu-id="0e19c-114">However, not all roots are special.</span></span> <span data-ttu-id="0e19c-115">Ad esempio, alcune directory principali non sono riferimenti deboli, i puntatori interni, bloccati o con conteggio dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="0e19c-115">For example, some roots are not weak references, interior pointers, pinned, or reference-counted.</span></span> <span data-ttu-id="0e19c-116">Per questo tipo radici, non sono presenti flag per indicare.</span><span class="sxs-lookup"><span data-stu-id="0e19c-116">For such roots, there are no flags to convey.</span></span> <span data-ttu-id="0e19c-117">Di conseguenza, i metodi che usano questa enumerazione, ad esempio la [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) metodo send 0 per la maschera di bit di flag che indica che tutti i flag sono disattivati.</span><span class="sxs-lookup"><span data-stu-id="0e19c-117">Therefore, methods that use this enumeration, such as the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method, send 0 for the flags bitmask, indicating that all flags are turned off.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e19c-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0e19c-118">Requirements</span></span>  
 <span data-ttu-id="0e19c-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e19c-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e19c-120">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0e19c-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0e19c-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e19c-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e19c-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e19c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e19c-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e19c-123">See also</span></span>

- [<span data-ttu-id="0e19c-124">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="0e19c-124">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)

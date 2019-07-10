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
ms.openlocfilehash: 7f179e3b01d6c3b34dfa765565a0fc38d0ba867c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753692"
---
# <a name="corprfgcrootflags-enumeration"></a><span data-ttu-id="c4fc9-102">Enumerazione COR_PRF_GC_ROOT_FLAGS</span><span class="sxs-lookup"><span data-stu-id="c4fc9-102">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>
<span data-ttu-id="c4fc9-103">Indica una proprietà di una radice di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="c4fc9-103">Indicates a property of a garbage collection root.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4fc9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c4fc9-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="c4fc9-105">Membri</span><span class="sxs-lookup"><span data-stu-id="c4fc9-105">Members</span></span>  
  
|<span data-ttu-id="c4fc9-106">Member</span><span class="sxs-lookup"><span data-stu-id="c4fc9-106">Member</span></span>|<span data-ttu-id="c4fc9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c4fc9-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|<span data-ttu-id="c4fc9-108">La radice impedisce un'operazione di garbage collection di spostare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="c4fc9-108">The root prevents a garbage collection from moving the object.</span></span>|  
|`COR_PRF_GC_ROOT_WEAKREF`|<span data-ttu-id="c4fc9-109">La radice non impedisce l'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="c4fc9-109">The root does not prevent garbage collection.</span></span>|  
|`COR_PRF_GC_ROOT_INTERIOR`|<span data-ttu-id="c4fc9-110">La radice fa riferimento a un campo dell'oggetto anziché l'oggetto stesso.</span><span class="sxs-lookup"><span data-stu-id="c4fc9-110">The root refers to a field of the object rather than the object itself.</span></span>|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|<span data-ttu-id="c4fc9-111">Radice impedisce l'operazione di garbage collection se il conteggio dei riferimenti dell'oggetto è un determinato valore.</span><span class="sxs-lookup"><span data-stu-id="c4fc9-111">The root prevents garbage collection if the reference count of the object is a certain value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4fc9-112">Note</span><span class="sxs-lookup"><span data-stu-id="c4fc9-112">Remarks</span></span>  
 <span data-ttu-id="c4fc9-113">`COR_PRF_GC_ROOT_FLAGS` è una maschera di bit che fornisce informazioni aggiuntive sulle radici speciali.</span><span class="sxs-lookup"><span data-stu-id="c4fc9-113">`COR_PRF_GC_ROOT_FLAGS` is a bitmask that provides additional information about special roots.</span></span> <span data-ttu-id="c4fc9-114">Tuttavia, non tutte le radici sono speciali.</span><span class="sxs-lookup"><span data-stu-id="c4fc9-114">However, not all roots are special.</span></span> <span data-ttu-id="c4fc9-115">Ad esempio, alcune directory principali non sono riferimenti deboli, i puntatori interni, bloccati o con conteggio dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="c4fc9-115">For example, some roots are not weak references, interior pointers, pinned, or reference-counted.</span></span> <span data-ttu-id="c4fc9-116">Per questo tipo radici, non sono presenti flag per indicare.</span><span class="sxs-lookup"><span data-stu-id="c4fc9-116">For such roots, there are no flags to convey.</span></span> <span data-ttu-id="c4fc9-117">Di conseguenza, i metodi che usano questa enumerazione, ad esempio la [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) metodo send 0 per la maschera di bit di flag che indica che tutti i flag sono disattivati.</span><span class="sxs-lookup"><span data-stu-id="c4fc9-117">Therefore, methods that use this enumeration, such as the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method, send 0 for the flags bitmask, indicating that all flags are turned off.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4fc9-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c4fc9-118">Requirements</span></span>  
 <span data-ttu-id="c4fc9-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4fc9-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4fc9-120">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c4fc9-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c4fc9-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4fc9-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4fc9-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4fc9-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4fc9-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4fc9-123">See also</span></span>

- [<span data-ttu-id="c4fc9-124">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="c4fc9-124">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)

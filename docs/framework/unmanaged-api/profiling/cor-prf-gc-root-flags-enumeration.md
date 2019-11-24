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
ms.openlocfilehash: 174486a88192bd5ff11074930d5ad3375603f8a5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449465"
---
# <a name="cor_prf_gc_root_flags-enumeration"></a><span data-ttu-id="5910b-102">Enumerazione COR_PRF_GC_ROOT_FLAGS</span><span class="sxs-lookup"><span data-stu-id="5910b-102">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>
<span data-ttu-id="5910b-103">Indicates a property of a garbage collection root.</span><span class="sxs-lookup"><span data-stu-id="5910b-103">Indicates a property of a garbage collection root.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5910b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5910b-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="5910b-105">Members</span><span class="sxs-lookup"><span data-stu-id="5910b-105">Members</span></span>  
  
|<span data-ttu-id="5910b-106">Member</span><span class="sxs-lookup"><span data-stu-id="5910b-106">Member</span></span>|<span data-ttu-id="5910b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5910b-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|<span data-ttu-id="5910b-108">The root prevents a garbage collection from moving the object.</span><span class="sxs-lookup"><span data-stu-id="5910b-108">The root prevents a garbage collection from moving the object.</span></span>|  
|`COR_PRF_GC_ROOT_WEAKREF`|<span data-ttu-id="5910b-109">The root does not prevent garbage collection.</span><span class="sxs-lookup"><span data-stu-id="5910b-109">The root does not prevent garbage collection.</span></span>|  
|`COR_PRF_GC_ROOT_INTERIOR`|<span data-ttu-id="5910b-110">The root refers to a field of the object rather than the object itself.</span><span class="sxs-lookup"><span data-stu-id="5910b-110">The root refers to a field of the object rather than the object itself.</span></span>|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|<span data-ttu-id="5910b-111">The root prevents garbage collection if the reference count of the object is a certain value.</span><span class="sxs-lookup"><span data-stu-id="5910b-111">The root prevents garbage collection if the reference count of the object is a certain value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5910b-112">Note</span><span class="sxs-lookup"><span data-stu-id="5910b-112">Remarks</span></span>  
 <span data-ttu-id="5910b-113">`COR_PRF_GC_ROOT_FLAGS` is a bitmask that provides additional information about special roots.</span><span class="sxs-lookup"><span data-stu-id="5910b-113">`COR_PRF_GC_ROOT_FLAGS` is a bitmask that provides additional information about special roots.</span></span> <span data-ttu-id="5910b-114">However, not all roots are special.</span><span class="sxs-lookup"><span data-stu-id="5910b-114">However, not all roots are special.</span></span> <span data-ttu-id="5910b-115">For example, some roots are not weak references, interior pointers, pinned, or reference-counted.</span><span class="sxs-lookup"><span data-stu-id="5910b-115">For example, some roots are not weak references, interior pointers, pinned, or reference-counted.</span></span> <span data-ttu-id="5910b-116">For such roots, there are no flags to convey.</span><span class="sxs-lookup"><span data-stu-id="5910b-116">For such roots, there are no flags to convey.</span></span> <span data-ttu-id="5910b-117">Therefore, methods that use this enumeration, such as the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method, send 0 for the flags bitmask, indicating that all flags are turned off.</span><span class="sxs-lookup"><span data-stu-id="5910b-117">Therefore, methods that use this enumeration, such as the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method, send 0 for the flags bitmask, indicating that all flags are turned off.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5910b-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5910b-118">Requirements</span></span>  
 <span data-ttu-id="5910b-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5910b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5910b-120">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5910b-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5910b-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5910b-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5910b-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5910b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5910b-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5910b-123">See also</span></span>

- [<span data-ttu-id="5910b-124">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="5910b-124">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)

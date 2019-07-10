---
title: Enumerazione COR_PRF_GC_ROOT_KIND
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_ROOT_KIND
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_ROOT_KIND
helpviewer_keywords:
- COR_PRF_GC_ROOT_KIND enumeration [.NET Framework profiling]
ms.assetid: b9fb1c03-417f-41d4-aed4-02cb4ade8def
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4b7a4c8dfc9e082b29d462b835886d6bf252bb39
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753675"
---
# <a name="corprfgcrootkind-enumeration"></a><span data-ttu-id="34753-102">Enumerazione COR_PRF_GC_ROOT_KIND</span><span class="sxs-lookup"><span data-stu-id="34753-102">COR_PRF_GC_ROOT_KIND Enumeration</span></span>
<span data-ttu-id="34753-103">Indica il tipo di radice di garbage collection che è esposto dal [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="34753-103">Indicates the kind of garbage collection root that is exposed by the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34753-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="34753-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_STACK = 1,  
    COR_PRF_GC_ROOT_FINALIZER = 2,  
    COR_PRF_GC_ROOT_HANDLE = 3,  
    COR_PRF_GC_ROOT_OTHER = 0  
} COR_PRF_GC_ROOT_KIND;  
```  
  
## <a name="members"></a><span data-ttu-id="34753-105">Membri</span><span class="sxs-lookup"><span data-stu-id="34753-105">Members</span></span>  
  
|<span data-ttu-id="34753-106">Member</span><span class="sxs-lookup"><span data-stu-id="34753-106">Member</span></span>|<span data-ttu-id="34753-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="34753-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_STACK`|<span data-ttu-id="34753-108">La radice è una variabile nello stack.</span><span class="sxs-lookup"><span data-stu-id="34753-108">The root is a variable on the stack.</span></span>|  
|`COR_PRF_GC_ROOT_FINALIZER`|<span data-ttu-id="34753-109">La radice è una voce nella coda del finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="34753-109">The root is an entry in the finalizer queue.</span></span>|  
|`COR_PRF_GC_ROOT_HANDLE`|<span data-ttu-id="34753-110">La radice è un handle di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="34753-110">The root is a garbage collection handle.</span></span>|  
|`COR_PRF_GC_ROOT_OTHER`|<span data-ttu-id="34753-111">Il tipo di radice non è specificato.</span><span class="sxs-lookup"><span data-stu-id="34753-111">The kind of root is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="34753-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="34753-112">Requirements</span></span>  
 <span data-ttu-id="34753-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34753-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34753-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="34753-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="34753-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34753-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34753-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34753-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34753-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34753-117">See also</span></span>

- [<span data-ttu-id="34753-118">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="34753-118">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)

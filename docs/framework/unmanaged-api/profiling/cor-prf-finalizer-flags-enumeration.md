---
title: Enumerazione COR_PRF_FINALIZER_FLAGS
ms.date: 03/30/2017
api_name:
- COR_PRF_FINALIZER_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FINALIZER_FLAGS
helpviewer_keywords:
- COR_PRF_FINALIZER_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 297d7721-3911-4f36-9e34-d9da0c33e22a
topic_type:
- apiref
ms.openlocfilehash: 5e718d05f033cc46fa460a81f6816a13ec32476d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428356"
---
# <a name="cor_prf_finalizer_flags-enumeration"></a><span data-ttu-id="b34ec-102">Enumerazione COR_PRF_FINALIZER_FLAGS</span><span class="sxs-lookup"><span data-stu-id="b34ec-102">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>
<span data-ttu-id="b34ec-103">Descrive il finalizzatore per un oggetto.</span><span class="sxs-lookup"><span data-stu-id="b34ec-103">Describes the finalizer for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b34ec-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b34ec-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_FINALIZER_CRITICAL = 0x1  
} COR_PRF_FINALIZER_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="b34ec-105">Membri</span><span class="sxs-lookup"><span data-stu-id="b34ec-105">Members</span></span>  
  
|<span data-ttu-id="b34ec-106">Membro</span><span class="sxs-lookup"><span data-stu-id="b34ec-106">Member</span></span>|<span data-ttu-id="b34ec-107">description</span><span class="sxs-lookup"><span data-stu-id="b34ec-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FINALIZER_CRITICAL`|<span data-ttu-id="b34ec-108">Il finalizzatore è di importanza critica.</span><span class="sxs-lookup"><span data-stu-id="b34ec-108">The finalizer is critical.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b34ec-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b34ec-109">Remarks</span></span>  
 <span data-ttu-id="b34ec-110">L'enumerazione `COR_PRF_FINALIZER_FLAGS` viene utilizzata dal metodo [ICorProfilerCallback2:: FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) per descrivere il finalizzatore per un oggetto.</span><span class="sxs-lookup"><span data-stu-id="b34ec-110">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b34ec-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b34ec-111">Requirements</span></span>  
 <span data-ttu-id="b34ec-112">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b34ec-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b34ec-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b34ec-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b34ec-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b34ec-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b34ec-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b34ec-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b34ec-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b34ec-116">See also</span></span>

- [<span data-ttu-id="b34ec-117">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="b34ec-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)

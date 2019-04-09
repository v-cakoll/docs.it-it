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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d5037f335e8d66c341d70d91d955a1ac7571b823
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59123760"
---
# <a name="corprffinalizerflags-enumeration"></a><span data-ttu-id="bb7fe-102">Enumerazione COR_PRF_FINALIZER_FLAGS</span><span class="sxs-lookup"><span data-stu-id="bb7fe-102">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>
<span data-ttu-id="bb7fe-103">Descrive il finalizzatore per un oggetto.</span><span class="sxs-lookup"><span data-stu-id="bb7fe-103">Describes the finalizer for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb7fe-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bb7fe-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_FINALIZER_CRITICAL = 0x1  
} COR_PRF_FINALIZER_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="bb7fe-105">Membri</span><span class="sxs-lookup"><span data-stu-id="bb7fe-105">Members</span></span>  
  
|<span data-ttu-id="bb7fe-106">Member</span><span class="sxs-lookup"><span data-stu-id="bb7fe-106">Member</span></span>|<span data-ttu-id="bb7fe-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb7fe-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FINALIZER_CRITICAL`|<span data-ttu-id="bb7fe-108">Il finalizzatore è fondamentale.</span><span class="sxs-lookup"><span data-stu-id="bb7fe-108">The finalizer is critical.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb7fe-109">Note</span><span class="sxs-lookup"><span data-stu-id="bb7fe-109">Remarks</span></span>  
 <span data-ttu-id="bb7fe-110">Il `COR_PRF_FINALIZER_FLAGS` enumerazione viene utilizzata per il [ICorProfilerCallback2::FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) metodo per descrivere il finalizzatore per un oggetto.</span><span class="sxs-lookup"><span data-stu-id="bb7fe-110">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb7fe-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bb7fe-111">Requirements</span></span>  
 <span data-ttu-id="bb7fe-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb7fe-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb7fe-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bb7fe-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bb7fe-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb7fe-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="bb7fe-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="bb7fe-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bb7fe-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb7fe-116">See also</span></span>

- [<span data-ttu-id="bb7fe-117">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="bb7fe-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)

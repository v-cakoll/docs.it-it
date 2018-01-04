---
title: Enumerazione COR_PRF_FINALIZER_FLAGS
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_FINALIZER_FLAGS
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_FINALIZER_FLAGS
helpviewer_keywords: COR_PRF_FINALIZER_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 297d7721-3911-4f36-9e34-d9da0c33e22a
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae0941e962b2fc1b08f0defb692038bd5fcf885a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="corprffinalizerflags-enumeration"></a><span data-ttu-id="0152e-102">Enumerazione COR_PRF_FINALIZER_FLAGS</span><span class="sxs-lookup"><span data-stu-id="0152e-102">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>
<span data-ttu-id="0152e-103">Descrive il finalizzatore per un oggetto.</span><span class="sxs-lookup"><span data-stu-id="0152e-103">Describes the finalizer for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0152e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0152e-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_FINALIZER_CRITICAL = 0x1  
} COR_PRF_FINALIZER_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="0152e-105">Membri</span><span class="sxs-lookup"><span data-stu-id="0152e-105">Members</span></span>  
  
|<span data-ttu-id="0152e-106">Membro</span><span class="sxs-lookup"><span data-stu-id="0152e-106">Member</span></span>|<span data-ttu-id="0152e-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0152e-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FINALIZER_CRITICAL`|<span data-ttu-id="0152e-108">Il finalizzatore è fondamentale.</span><span class="sxs-lookup"><span data-stu-id="0152e-108">The finalizer is critical.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0152e-109">Note</span><span class="sxs-lookup"><span data-stu-id="0152e-109">Remarks</span></span>  
 <span data-ttu-id="0152e-110">Il `COR_PRF_FINALIZER_FLAGS` enumerazione viene utilizzata per la [ICorProfilerCallback2:: FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) per descrivere il finalizzatore per un oggetto.</span><span class="sxs-lookup"><span data-stu-id="0152e-110">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0152e-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0152e-111">Requirements</span></span>  
 <span data-ttu-id="0152e-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0152e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0152e-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0152e-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0152e-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0152e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0152e-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0152e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0152e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0152e-116">See Also</span></span>  
 [<span data-ttu-id="0152e-117">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="0152e-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)

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
ms.openlocfilehash: daca2849908a7798b588ff06f6e117d412db1b33
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867269"
---
# <a name="cor_prf_finalizer_flags-enumeration"></a><span data-ttu-id="0e0c0-102">Enumerazione COR_PRF_FINALIZER_FLAGS</span><span class="sxs-lookup"><span data-stu-id="0e0c0-102">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>
<span data-ttu-id="0e0c0-103">Descrive il finalizzatore per un oggetto.</span><span class="sxs-lookup"><span data-stu-id="0e0c0-103">Describes the finalizer for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e0c0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0e0c0-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_FINALIZER_CRITICAL = 0x1  
} COR_PRF_FINALIZER_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="0e0c0-105">Membri</span><span class="sxs-lookup"><span data-stu-id="0e0c0-105">Members</span></span>  
  
|<span data-ttu-id="0e0c0-106">Member</span><span class="sxs-lookup"><span data-stu-id="0e0c0-106">Member</span></span>|<span data-ttu-id="0e0c0-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0e0c0-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FINALIZER_CRITICAL`|<span data-ttu-id="0e0c0-108">Il finalizzatore è di importanza critica.</span><span class="sxs-lookup"><span data-stu-id="0e0c0-108">The finalizer is critical.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e0c0-109">Note</span><span class="sxs-lookup"><span data-stu-id="0e0c0-109">Remarks</span></span>  
 <span data-ttu-id="0e0c0-110">L'enumerazione `COR_PRF_FINALIZER_FLAGS` viene utilizzata dal metodo [ICorProfilerCallback2:: FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md) per descrivere il finalizzatore per un oggetto.</span><span class="sxs-lookup"><span data-stu-id="0e0c0-110">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e0c0-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="0e0c0-111">Requirements</span></span>  
 <span data-ttu-id="0e0c0-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e0c0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e0c0-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0e0c0-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0e0c0-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e0c0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e0c0-115">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e0c0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e0c0-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e0c0-116">See also</span></span>

- [<span data-ttu-id="0e0c0-117">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="0e0c0-117">Profiling Enumerations</span></span>](profiling-enumerations.md)

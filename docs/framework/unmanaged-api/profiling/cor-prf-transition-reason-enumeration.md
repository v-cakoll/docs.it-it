---
title: Enumerazione COR_PRF_TRANSITION_REASON
ms.date: 03/30/2017
api_name:
- COR_PRF_TRANSITION_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_TRANSITION_REASON
helpviewer_keywords:
- COR_PRF_TRANSITION_REASON enumeration [.NET Framework profiling]
ms.assetid: da941118-01b7-4197-ae5b-9f2f8adcd623
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2556196b7c8f81709e6880962e8ff36e126dd8b0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61599039"
---
# <a name="corprftransitionreason-enumeration"></a><span data-ttu-id="e2340-102">Enumerazione COR_PRF_TRANSITION_REASON</span><span class="sxs-lookup"><span data-stu-id="e2340-102">COR_PRF_TRANSITION_REASON Enumeration</span></span>
<span data-ttu-id="e2340-103">Indica il motivo di una transizione da codice gestito a codice non gestito o viceversa.</span><span class="sxs-lookup"><span data-stu-id="e2340-103">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2340-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2340-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_TRANSITION_CALL,  
    COR_PRF_TRANSITION_RETURN  
} COR_PRF_TRANSITION_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="e2340-105">Membri</span><span class="sxs-lookup"><span data-stu-id="e2340-105">Members</span></span>  
  
|<span data-ttu-id="e2340-106">Member</span><span class="sxs-lookup"><span data-stu-id="e2340-106">Member</span></span>|<span data-ttu-id="e2340-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e2340-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_TRANSITION_CALL`|<span data-ttu-id="e2340-108">La transizione è dovuto a una chiamata in una funzione.</span><span class="sxs-lookup"><span data-stu-id="e2340-108">The transition is due to a call into a function.</span></span>|  
|`COR_PRF_TRANSITION_RETURN`|<span data-ttu-id="e2340-109">La transizione è dovuto a una restituzione da una funzione.</span><span class="sxs-lookup"><span data-stu-id="e2340-109">The transition is due to a return from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2340-110">Note</span><span class="sxs-lookup"><span data-stu-id="e2340-110">Remarks</span></span>  
 <span data-ttu-id="e2340-111">Quando si verifica una transizione, il profiler riceve un' [ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) oppure [UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) callback, ciascuno dei quali fornisce un valore di `COR_PRF_TRANSITION_REASON` enumerazione per indicare il motivo per la transizione.</span><span class="sxs-lookup"><span data-stu-id="e2340-111">When a transition occurs, the profiler receives an [ICorProfilerCallback::ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) or [ICorProfilerCallback::UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) callback, either of which provides a value of the `COR_PRF_TRANSITION_REASON` enumeration to indicate the reason for the transition.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2340-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e2340-112">Requirements</span></span>  
 <span data-ttu-id="e2340-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2340-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2340-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e2340-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e2340-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2340-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2340-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2340-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

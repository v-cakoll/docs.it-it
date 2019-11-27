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
ms.openlocfilehash: 6d8b408675127cde399a8346f2b9734a0e038cb5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427136"
---
# <a name="cor_prf_transition_reason-enumeration"></a><span data-ttu-id="e1b5e-102">Enumerazione COR_PRF_TRANSITION_REASON</span><span class="sxs-lookup"><span data-stu-id="e1b5e-102">COR_PRF_TRANSITION_REASON Enumeration</span></span>
<span data-ttu-id="e1b5e-103">Indica il motivo di una transizione da codice gestito a codice non gestito o viceversa.</span><span class="sxs-lookup"><span data-stu-id="e1b5e-103">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1b5e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e1b5e-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_TRANSITION_CALL,  
    COR_PRF_TRANSITION_RETURN  
} COR_PRF_TRANSITION_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="e1b5e-105">Members</span><span class="sxs-lookup"><span data-stu-id="e1b5e-105">Members</span></span>  
  
|<span data-ttu-id="e1b5e-106">Membro</span><span class="sxs-lookup"><span data-stu-id="e1b5e-106">Member</span></span>|<span data-ttu-id="e1b5e-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e1b5e-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_TRANSITION_CALL`|<span data-ttu-id="e1b5e-108">La transizione è dovuta a una chiamata in una funzione.</span><span class="sxs-lookup"><span data-stu-id="e1b5e-108">The transition is due to a call into a function.</span></span>|  
|`COR_PRF_TRANSITION_RETURN`|<span data-ttu-id="e1b5e-109">La transizione è dovuta a un ritorno da una funzione.</span><span class="sxs-lookup"><span data-stu-id="e1b5e-109">The transition is due to a return from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1b5e-110">Note</span><span class="sxs-lookup"><span data-stu-id="e1b5e-110">Remarks</span></span>  
 <span data-ttu-id="e1b5e-111">Quando si verifica una transizione, il profiler riceve un callback [ICorProfilerCallback:: ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) o [ICorProfilerCallback:: UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) , uno dei quali fornisce un valore dell'enumerazione `COR_PRF_TRANSITION_REASON` per indicare il motivo della transizione.</span><span class="sxs-lookup"><span data-stu-id="e1b5e-111">When a transition occurs, the profiler receives an [ICorProfilerCallback::ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) or [ICorProfilerCallback::UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) callback, either of which provides a value of the `COR_PRF_TRANSITION_REASON` enumeration to indicate the reason for the transition.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1b5e-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e1b5e-112">Requirements</span></span>  
 <span data-ttu-id="e1b5e-113">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1b5e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1b5e-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e1b5e-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e1b5e-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1b5e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1b5e-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1b5e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

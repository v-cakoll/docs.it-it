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
ms.openlocfilehash: 1c3c311fd431b6c0b18af3d6516973b2471cfabd
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867048"
---
# <a name="cor_prf_transition_reason-enumeration"></a><span data-ttu-id="d8a23-102">Enumerazione COR_PRF_TRANSITION_REASON</span><span class="sxs-lookup"><span data-stu-id="d8a23-102">COR_PRF_TRANSITION_REASON Enumeration</span></span>
<span data-ttu-id="d8a23-103">Indica il motivo di una transizione da codice gestito a codice non gestito o viceversa.</span><span class="sxs-lookup"><span data-stu-id="d8a23-103">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8a23-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d8a23-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_TRANSITION_CALL,  
    COR_PRF_TRANSITION_RETURN  
} COR_PRF_TRANSITION_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="d8a23-105">Membri</span><span class="sxs-lookup"><span data-stu-id="d8a23-105">Members</span></span>  
  
|<span data-ttu-id="d8a23-106">Member</span><span class="sxs-lookup"><span data-stu-id="d8a23-106">Member</span></span>|<span data-ttu-id="d8a23-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d8a23-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_TRANSITION_CALL`|<span data-ttu-id="d8a23-108">La transizione è dovuta a una chiamata in una funzione.</span><span class="sxs-lookup"><span data-stu-id="d8a23-108">The transition is due to a call into a function.</span></span>|  
|`COR_PRF_TRANSITION_RETURN`|<span data-ttu-id="d8a23-109">La transizione è dovuta a un ritorno da una funzione.</span><span class="sxs-lookup"><span data-stu-id="d8a23-109">The transition is due to a return from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8a23-110">Note</span><span class="sxs-lookup"><span data-stu-id="d8a23-110">Remarks</span></span>  
 <span data-ttu-id="d8a23-111">Quando si verifica una transizione, il profiler riceve un callback [ICorProfilerCallback:: ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md) o [ICorProfilerCallback:: UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md) , uno dei quali fornisce un valore dell'enumerazione `COR_PRF_TRANSITION_REASON` per indicare il motivo della transizione.</span><span class="sxs-lookup"><span data-stu-id="d8a23-111">When a transition occurs, the profiler receives an [ICorProfilerCallback::ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md) or [ICorProfilerCallback::UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md) callback, either of which provides a value of the `COR_PRF_TRANSITION_REASON` enumeration to indicate the reason for the transition.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8a23-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="d8a23-112">Requirements</span></span>  
 <span data-ttu-id="d8a23-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8a23-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8a23-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d8a23-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d8a23-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8a23-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8a23-116">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8a23-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

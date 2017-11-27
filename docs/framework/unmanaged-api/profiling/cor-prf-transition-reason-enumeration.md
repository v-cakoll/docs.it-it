---
title: Enumerazione COR_PRF_TRANSITION_REASON
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_TRANSITION_REASON
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_TRANSITION_REASON
helpviewer_keywords: COR_PRF_TRANSITION_REASON enumeration [.NET Framework profiling]
ms.assetid: da941118-01b7-4197-ae5b-9f2f8adcd623
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9f11b5fb5409ee30b0456e0c562545718ed46bb6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="corprftransitionreason-enumeration"></a><span data-ttu-id="7eda8-102">Enumerazione COR_PRF_TRANSITION_REASON</span><span class="sxs-lookup"><span data-stu-id="7eda8-102">COR_PRF_TRANSITION_REASON Enumeration</span></span>
<span data-ttu-id="7eda8-103">Indica il motivo di una transizione da codice gestito a codice non gestito o viceversa.</span><span class="sxs-lookup"><span data-stu-id="7eda8-103">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7eda8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7eda8-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_TRANSITION_CALL,  
    COR_PRF_TRANSITION_RETURN  
} COR_PRF_TRANSITION_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="7eda8-105">Membri</span><span class="sxs-lookup"><span data-stu-id="7eda8-105">Members</span></span>  
  
|<span data-ttu-id="7eda8-106">Membro</span><span class="sxs-lookup"><span data-stu-id="7eda8-106">Member</span></span>|<span data-ttu-id="7eda8-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7eda8-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_TRANSITION_CALL`|<span data-ttu-id="7eda8-108">La transizione è dovuto a una chiamata a una funzione.</span><span class="sxs-lookup"><span data-stu-id="7eda8-108">The transition is due to a call into a function.</span></span>|  
|`COR_PRF_TRANSITION_RETURN`|<span data-ttu-id="7eda8-109">La transizione è dovuto a un ritorno da una funzione.</span><span class="sxs-lookup"><span data-stu-id="7eda8-109">The transition is due to a return from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7eda8-110">Note</span><span class="sxs-lookup"><span data-stu-id="7eda8-110">Remarks</span></span>  
 <span data-ttu-id="7eda8-111">Quando si verifica una transizione, il profiler avrà ricevuto un [ICorProfilerCallback:: ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) o [ICorProfilerCallback:: UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) callback, uno dei quali fornisce un valore di `COR_PRF_TRANSITION_REASON` enumerazione per indicare il motivo della transizione.</span><span class="sxs-lookup"><span data-stu-id="7eda8-111">When a transition occurs, the profiler receives an [ICorProfilerCallback::ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) or [ICorProfilerCallback::UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) callback, either of which provides a value of the `COR_PRF_TRANSITION_REASON` enumeration to indicate the reason for the transition.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7eda8-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7eda8-112">Requirements</span></span>  
 <span data-ttu-id="7eda8-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7eda8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7eda8-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7eda8-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7eda8-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7eda8-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7eda8-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7eda8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

---
title: Metodo ICorDebugController::SetAllThreadsDebugState
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugController.SetAllThreadsDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::SetAllThreadsDebugState
helpviewer_keywords:
- SetAllThreadsDebugState method [.NET Framework debugging]
- ICorDebugController::SetAllThreadsDebugState method [.NET Framework debugging]
ms.assetid: bdda4bd7-4743-4d58-a22b-8067e967db95
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b8c9904c3c86e405660dcafe9963fe05049524b4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcontrollersetallthreadsdebugstate-method"></a><span data-ttu-id="4af8b-102">Metodo ICorDebugController::SetAllThreadsDebugState</span><span class="sxs-lookup"><span data-stu-id="4af8b-102">ICorDebugController::SetAllThreadsDebugState Method</span></span>
<span data-ttu-id="4af8b-103">Imposta lo stato di debug di tutti i thread gestiti nel processo.</span><span class="sxs-lookup"><span data-stu-id="4af8b-103">Sets the debug state of all managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4af8b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4af8b-104">Syntax</span></span>  
  
```  
HRESULT SetAllThreadsDebugState (  
    [in] CorDebugThreadState  state,  
    [in] ICorDebugThread      *pExceptThisThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4af8b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4af8b-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="4af8b-106">[in] Valore dell'enumerazione che specifica lo stato del thread per il debug "CorDebugThreadState".</span><span class="sxs-lookup"><span data-stu-id="4af8b-106">[in] A value of the "CorDebugThreadState" enumeration that specifies the state of the thread for debugging.</span></span>  
  
 `pExceptThisThread`  
 <span data-ttu-id="4af8b-107">[in] Un puntatore a un oggetto "ICorDebugThread" che rappresenta un thread da escludere dalle impostazioni dello stato di debug.</span><span class="sxs-lookup"><span data-stu-id="4af8b-107">[in] A pointer to an "ICorDebugThread" object that represents a thread to be exempted from the debug state setting.</span></span> <span data-ttu-id="4af8b-108">Se questo valore è null, verrà escluso alcun thread.</span><span class="sxs-lookup"><span data-stu-id="4af8b-108">If this value is null, no thread is exempted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4af8b-109">Note</span><span class="sxs-lookup"><span data-stu-id="4af8b-109">Remarks</span></span>  
 <span data-ttu-id="4af8b-110">Il `SetAllThreadsDebugState` metodo può influire sui thread che non sono visibili tramite [EnumerateThreads (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md), pertanto thread sospesi con il `SetAllThreadsDebugState` metodo dovrà essere ripreso con il `SetAllThreadsDebugState` metodo.</span><span class="sxs-lookup"><span data-stu-id="4af8b-110">The `SetAllThreadsDebugState` method may affect threads that are not visible via [EnumerateThreads Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md), so threads that were suspended with the `SetAllThreadsDebugState` method will need to be resumed with the `SetAllThreadsDebugState` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4af8b-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4af8b-111">Requirements</span></span>  
 <span data-ttu-id="4af8b-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4af8b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4af8b-113">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="4af8b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4af8b-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4af8b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4af8b-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4af8b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4af8b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4af8b-116">See Also</span></span>  
 

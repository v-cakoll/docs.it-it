---
title: Metodo ICorDebugController::SetAllThreadsDebugState
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 280dc3f0271d7326fe4c22b813abebfd4d45c89e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138476"
---
# <a name="icordebugcontrollersetallthreadsdebugstate-method"></a><span data-ttu-id="78b33-102">Metodo ICorDebugController::SetAllThreadsDebugState</span><span class="sxs-lookup"><span data-stu-id="78b33-102">ICorDebugController::SetAllThreadsDebugState Method</span></span>
<span data-ttu-id="78b33-103">Imposta lo stato di debug di tutti i thread gestiti nel processo.</span><span class="sxs-lookup"><span data-stu-id="78b33-103">Sets the debug state of all managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78b33-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="78b33-104">Syntax</span></span>  
  
```  
HRESULT SetAllThreadsDebugState (  
    [in] CorDebugThreadState  state,  
    [in] ICorDebugThread      *pExceptThisThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78b33-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="78b33-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="78b33-106">[in] Valore dell'enumerazione "CorDebugThreadState" che specifica lo stato del thread per eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="78b33-106">[in] A value of the "CorDebugThreadState" enumeration that specifies the state of the thread for debugging.</span></span>  
  
 `pExceptThisThread`  
 <span data-ttu-id="78b33-107">[in] Un puntatore a un oggetto "ICorDebugThread" che rappresenta un thread da escludere dalle impostazioni dello stato di debug.</span><span class="sxs-lookup"><span data-stu-id="78b33-107">[in] A pointer to an "ICorDebugThread" object that represents a thread to be exempted from the debug state setting.</span></span> <span data-ttu-id="78b33-108">Se questo valore è null, non viene esentato nessun thread.</span><span class="sxs-lookup"><span data-stu-id="78b33-108">If this value is null, no thread is exempted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78b33-109">Note</span><span class="sxs-lookup"><span data-stu-id="78b33-109">Remarks</span></span>  
 <span data-ttu-id="78b33-110">Il `SetAllThreadsDebugState` metodo può influire sui thread che non sono visibili tramite [EnumerateThreads (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md), in questo thread sospesi con il `SetAllThreadsDebugState` metodo dovrà essere ripreso con il `SetAllThreadsDebugState` (metodo).</span><span class="sxs-lookup"><span data-stu-id="78b33-110">The `SetAllThreadsDebugState` method may affect threads that are not visible via [EnumerateThreads Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md), so threads that were suspended with the `SetAllThreadsDebugState` method will need to be resumed with the `SetAllThreadsDebugState` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78b33-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="78b33-111">Requirements</span></span>  
 <span data-ttu-id="78b33-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78b33-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78b33-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="78b33-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="78b33-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="78b33-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="78b33-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="78b33-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="78b33-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78b33-116">See also</span></span>

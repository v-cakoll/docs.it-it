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
ms.openlocfilehash: 8ee396c512dca2bea0a7a9737d5515defce4b2b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415129"
---
# <a name="icordebugcontrollersetallthreadsdebugstate-method"></a><span data-ttu-id="11363-102">Metodo ICorDebugController::SetAllThreadsDebugState</span><span class="sxs-lookup"><span data-stu-id="11363-102">ICorDebugController::SetAllThreadsDebugState Method</span></span>
<span data-ttu-id="11363-103">Imposta lo stato di debug di tutti i thread gestiti nel processo.</span><span class="sxs-lookup"><span data-stu-id="11363-103">Sets the debug state of all managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11363-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="11363-104">Syntax</span></span>  
  
```  
HRESULT SetAllThreadsDebugState (  
    [in] CorDebugThreadState  state,  
    [in] ICorDebugThread      *pExceptThisThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="11363-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="11363-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="11363-106">[in] Valore dell'enumerazione che specifica lo stato del thread per il debug "CorDebugThreadState".</span><span class="sxs-lookup"><span data-stu-id="11363-106">[in] A value of the "CorDebugThreadState" enumeration that specifies the state of the thread for debugging.</span></span>  
  
 `pExceptThisThread`  
 <span data-ttu-id="11363-107">[in] Un puntatore a un oggetto "ICorDebugThread" che rappresenta un thread da escludere dalle impostazioni dello stato di debug.</span><span class="sxs-lookup"><span data-stu-id="11363-107">[in] A pointer to an "ICorDebugThread" object that represents a thread to be exempted from the debug state setting.</span></span> <span data-ttu-id="11363-108">Se questo valore è null, verrà escluso alcun thread.</span><span class="sxs-lookup"><span data-stu-id="11363-108">If this value is null, no thread is exempted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11363-109">Note</span><span class="sxs-lookup"><span data-stu-id="11363-109">Remarks</span></span>  
 <span data-ttu-id="11363-110">Il `SetAllThreadsDebugState` metodo può influire sui thread che non sono visibili tramite [EnumerateThreads (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md), pertanto thread sospesi con il `SetAllThreadsDebugState` metodo dovrà essere ripreso con il `SetAllThreadsDebugState` metodo.</span><span class="sxs-lookup"><span data-stu-id="11363-110">The `SetAllThreadsDebugState` method may affect threads that are not visible via [EnumerateThreads Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md), so threads that were suspended with the `SetAllThreadsDebugState` method will need to be resumed with the `SetAllThreadsDebugState` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11363-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="11363-111">Requirements</span></span>  
 <span data-ttu-id="11363-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11363-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11363-113">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="11363-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11363-114">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="11363-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11363-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11363-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11363-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11363-116">See Also</span></span>  
 

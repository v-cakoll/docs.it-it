---
title: Metodo ICorDebugController::HasQueuedCallbacks
ms.date: 03/30/2017
api_name:
- ICorDebugController.HasQueuedCallbacks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::HasQueuedCallbacks
helpviewer_keywords:
- HasQueuedCallbacks method [.NET Framework debugging]
- ICorDebugController::HasQueuedCallbacks method [.NET Framework debugging]
ms.assetid: 0d6a1cd9-370b-4462-adbf-e3980e897ea7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eba265b727d00690ab77c6ae831e954d59df7c50
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411610"
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a><span data-ttu-id="a8abd-102">Metodo ICorDebugController::HasQueuedCallbacks</span><span class="sxs-lookup"><span data-stu-id="a8abd-102">ICorDebugController::HasQueuedCallbacks Method</span></span>
<span data-ttu-id="a8abd-103">Ottiene un valore che indica se i callback gestiti attualmente in coda per il thread specificato.</span><span class="sxs-lookup"><span data-stu-id="a8abd-103">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8abd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a8abd-104">Syntax</span></span>  
  
```  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a8abd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a8abd-105">Parameters</span></span>  
 `pThread`  
 <span data-ttu-id="a8abd-106">[in] Un puntatore a un oggetto "ICorDebugThread" che rappresenta il thread.</span><span class="sxs-lookup"><span data-stu-id="a8abd-106">[in] A pointer to an "ICorDebugThread" object that represents the thread.</span></span>  
  
 `pbQueued`  
 <span data-ttu-id="a8abd-107">[out] Un puntatore a un valore che è `true` se qualsiasi callback gestiti sono attualmente in coda per il thread specificato; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="a8abd-107">[out] A pointer to a value that is `true` if any managed callbacks are currently queued for the specified thread; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="a8abd-108">Se si specifica null per il `pThread` parametro `HasQueuedCallbacks` restituirà `true` se non esistono attualmente callback gestiti in coda per uno o più thread.</span><span class="sxs-lookup"><span data-stu-id="a8abd-108">If null is specified for the `pThread` parameter, `HasQueuedCallbacks` will return `true` if there are currently managed callbacks queued for any thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8abd-109">Note</span><span class="sxs-lookup"><span data-stu-id="a8abd-109">Remarks</span></span>  
 <span data-ttu-id="a8abd-110">I callback saranno inviati uno alla volta, ogni volta che [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="a8abd-110">Callbacks will be dispatched one at a time, each time [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) is called.</span></span> <span data-ttu-id="a8abd-111">Il debugger è possibile controllare questo flag se si desiderano segnalare gli eventi di debug più che si verificano simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="a8abd-111">The debugger can check this flag if it wants to report multiple debugging events that occur simultaneously.</span></span>  
  
 <span data-ttu-id="a8abd-112">Quando si trovano nella coda degli eventi di debug, che si è già verificata, affinché il debugger deve svuotare l'intera coda per essere certi che dello stato dell'oggetto del debug.</span><span class="sxs-lookup"><span data-stu-id="a8abd-112">When debugging events are queued, they have already occurred, so the debugger must drain the entire queue to be sure of the state of the debuggee.</span></span> <span data-ttu-id="a8abd-113">(Chiamare `ICorDebugController::Continue` per svuotare la coda.) Ad esempio, se la coda contiene due eventi di debug nel thread *X*, e il debugger sospende il thread *X* dopo il primo evento di debug, quindi chiama `ICorDebugController::Continue`, il secondo evento di debug per thread *X* verranno inviati anche se il thread è stata sospesa.</span><span class="sxs-lookup"><span data-stu-id="a8abd-113">(Call `ICorDebugController::Continue` to drain the queue.) For example, if the queue contains two debugging events on thread *X*, and the debugger suspends thread *X* after the first debugging event and then calls `ICorDebugController::Continue`, the second debugging event for thread *X* will be dispatched although the thread has been suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8abd-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a8abd-114">Requirements</span></span>  
 <span data-ttu-id="a8abd-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8abd-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8abd-116">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="a8abd-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a8abd-117">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="a8abd-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8abd-118">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8abd-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8abd-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8abd-119">See Also</span></span>  
 

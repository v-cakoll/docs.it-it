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
ms.openlocfilehash: 0d17f51867b64780fca9b21c5f48c88db36343af
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748776"
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a><span data-ttu-id="9c886-102">Metodo ICorDebugController::HasQueuedCallbacks</span><span class="sxs-lookup"><span data-stu-id="9c886-102">ICorDebugController::HasQueuedCallbacks Method</span></span>
<span data-ttu-id="9c886-103">Ottiene un valore che indica se i callback gestiti attualmente in coda per il thread specificato.</span><span class="sxs-lookup"><span data-stu-id="9c886-103">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c886-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9c886-104">Syntax</span></span>  
  
```cpp  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c886-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9c886-105">Parameters</span></span>  
 `pThread`  
 <span data-ttu-id="9c886-106">[in] Un puntatore a un oggetto "ICorDebugThread" che rappresenta il thread.</span><span class="sxs-lookup"><span data-stu-id="9c886-106">[in] A pointer to an "ICorDebugThread" object that represents the thread.</span></span>  
  
 `pbQueued`  
 <span data-ttu-id="9c886-107">[out] Un puntatore a un valore che rappresenta `true` se i callback gestiti sono attualmente in coda per il thread specificato; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="9c886-107">[out] A pointer to a value that is `true` if any managed callbacks are currently queued for the specified thread; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="9c886-108">Se si specifica null per il `pThread` parametro, `HasQueuedCallbacks` restituirà `true` se sono presenti attualmente callback gestito accodati per uno o più thread.</span><span class="sxs-lookup"><span data-stu-id="9c886-108">If null is specified for the `pThread` parameter, `HasQueuedCallbacks` will return `true` if there are currently managed callbacks queued for any thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c886-109">Note</span><span class="sxs-lookup"><span data-stu-id="9c886-109">Remarks</span></span>  
 <span data-ttu-id="9c886-110">I callback saranno inviati uno alla volta, ogni volta che [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="9c886-110">Callbacks will be dispatched one at a time, each time [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) is called.</span></span> <span data-ttu-id="9c886-111">Il debugger può controllare questo flag se si desiderano segnalare gli eventi di debug più che si verificano contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="9c886-111">The debugger can check this flag if it wants to report multiple debugging events that occur simultaneously.</span></span>  
  
 <span data-ttu-id="9c886-112">Quando si trovano nella coda degli eventi di debug, essi essersi già verificati, in modo che il debugger è necessario eliminare l'intera coda per essere certi dello stato dell'oggetto del debug.</span><span class="sxs-lookup"><span data-stu-id="9c886-112">When debugging events are queued, they have already occurred, so the debugger must drain the entire queue to be sure of the state of the debuggee.</span></span> <span data-ttu-id="9c886-113">(Chiamare `ICorDebugController::Continue` per svuotare la coda.) Ad esempio, se la coda contiene due eventi di debug sul thread *X*, e il debugger sospende il thread *X* dopo il primo evento di debug e quindi chiama `ICorDebugController::Continue`, il secondo evento di debug per thread *X* verranno inviati anche se il thread è stata sospesa.</span><span class="sxs-lookup"><span data-stu-id="9c886-113">(Call `ICorDebugController::Continue` to drain the queue.) For example, if the queue contains two debugging events on thread *X*, and the debugger suspends thread *X* after the first debugging event and then calls `ICorDebugController::Continue`, the second debugging event for thread *X* will be dispatched although the thread has been suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c886-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9c886-114">Requirements</span></span>  
 <span data-ttu-id="9c886-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c886-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c886-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9c886-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c886-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c886-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c886-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c886-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c886-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c886-119">See also</span></span>

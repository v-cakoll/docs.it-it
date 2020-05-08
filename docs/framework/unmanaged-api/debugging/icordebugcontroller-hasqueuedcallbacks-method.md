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
ms.openlocfilehash: bd656445c2451d0583ddbc45e71c9e090bb80305
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892784"
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a><span data-ttu-id="24a73-102">Metodo ICorDebugController::HasQueuedCallbacks</span><span class="sxs-lookup"><span data-stu-id="24a73-102">ICorDebugController::HasQueuedCallbacks Method</span></span>
<span data-ttu-id="24a73-103">Ottiene un valore che indica se i callback gestiti sono attualmente in coda per il thread specificato.</span><span class="sxs-lookup"><span data-stu-id="24a73-103">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24a73-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="24a73-104">Syntax</span></span>  
  
```cpp  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24a73-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="24a73-105">Parameters</span></span>  
 `pThread`  
 <span data-ttu-id="24a73-106">in Puntatore a un oggetto "ICorDebugThread" che rappresenta il thread.</span><span class="sxs-lookup"><span data-stu-id="24a73-106">[in] A pointer to an "ICorDebugThread" object that represents the thread.</span></span>  
  
 `pbQueued`  
 <span data-ttu-id="24a73-107">out Puntatore a un valore che è `true` se sono attualmente presenti callback gestiti in coda per il thread specificato. in caso `false`contrario,.</span><span class="sxs-lookup"><span data-stu-id="24a73-107">[out] A pointer to a value that is `true` if any managed callbacks are currently queued for the specified thread; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="24a73-108">Se viene specificato null per il `pThread` parametro, `HasQueuedCallbacks` restituirà `true` se sono presenti callback attualmente gestiti in coda per qualsiasi thread.</span><span class="sxs-lookup"><span data-stu-id="24a73-108">If null is specified for the `pThread` parameter, `HasQueuedCallbacks` will return `true` if there are currently managed callbacks queued for any thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24a73-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="24a73-109">Remarks</span></span>  
 <span data-ttu-id="24a73-110">I callback verranno inviati uno alla volta, ogni volta che viene chiamato [ICorDebugController:: continue](icordebugcontroller-continue-method.md) .</span><span class="sxs-lookup"><span data-stu-id="24a73-110">Callbacks will be dispatched one at a time, each time [ICorDebugController::Continue](icordebugcontroller-continue-method.md) is called.</span></span> <span data-ttu-id="24a73-111">Il debugger può verificare questo flag se desidera segnalare più eventi di debug che si verificano simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="24a73-111">The debugger can check this flag if it wants to report multiple debugging events that occur simultaneously.</span></span>  
  
 <span data-ttu-id="24a73-112">Quando gli eventi di debug sono accodati, si sono già verificati, pertanto il debugger deve svuotare l'intera coda per assicurarsi che lo stato dell'oggetto del debug.</span><span class="sxs-lookup"><span data-stu-id="24a73-112">When debugging events are queued, they have already occurred, so the debugger must drain the entire queue to be sure of the state of the debuggee.</span></span> <span data-ttu-id="24a73-113">(Chiamare `ICorDebugController::Continue` per svuotare la coda). Se, ad esempio, la coda contiene due eventi di debug sul thread *x*e il debugger sospende il thread *x* dopo il primo evento di debug e `ICorDebugController::Continue`quindi chiama, il secondo evento di debug per il thread *x* verrà inviato anche se il thread è stato sospeso.</span><span class="sxs-lookup"><span data-stu-id="24a73-113">(Call `ICorDebugController::Continue` to drain the queue.) For example, if the queue contains two debugging events on thread *X*, and the debugger suspends thread *X* after the first debugging event and then calls `ICorDebugController::Continue`, the second debugging event for thread *X* will be dispatched although the thread has been suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24a73-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="24a73-114">Requirements</span></span>  
 <span data-ttu-id="24a73-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24a73-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24a73-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="24a73-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="24a73-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24a73-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24a73-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24a73-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24a73-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24a73-119">See also</span></span>

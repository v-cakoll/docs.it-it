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
ms.openlocfilehash: 51ee8b3631bffe9fd7fef4351e0aa67d1cbbe2c9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125392"
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a><span data-ttu-id="65b9b-102">Metodo ICorDebugController::HasQueuedCallbacks</span><span class="sxs-lookup"><span data-stu-id="65b9b-102">ICorDebugController::HasQueuedCallbacks Method</span></span>
<span data-ttu-id="65b9b-103">Ottiene un valore che indica se i callback gestiti sono attualmente in coda per il thread specificato.</span><span class="sxs-lookup"><span data-stu-id="65b9b-103">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65b9b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="65b9b-104">Syntax</span></span>  
  
```cpp  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65b9b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="65b9b-105">Parameters</span></span>  
 `pThread`  
 <span data-ttu-id="65b9b-106">in Puntatore a un oggetto "ICorDebugThread" che rappresenta il thread.</span><span class="sxs-lookup"><span data-stu-id="65b9b-106">[in] A pointer to an "ICorDebugThread" object that represents the thread.</span></span>  
  
 `pbQueued`  
 <span data-ttu-id="65b9b-107">out Puntatore a un valore `true` se sono attualmente presenti callback gestiti in coda per il thread specificato. in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="65b9b-107">[out] A pointer to a value that is `true` if any managed callbacks are currently queued for the specified thread; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="65b9b-108">Se viene specificato null per il parametro `pThread`, `HasQueuedCallbacks` restituirà `true` se sono presenti callback attualmente gestiti in coda per qualsiasi thread.</span><span class="sxs-lookup"><span data-stu-id="65b9b-108">If null is specified for the `pThread` parameter, `HasQueuedCallbacks` will return `true` if there are currently managed callbacks queued for any thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65b9b-109">Note</span><span class="sxs-lookup"><span data-stu-id="65b9b-109">Remarks</span></span>  
 <span data-ttu-id="65b9b-110">I callback verranno inviati uno alla volta, ogni volta che viene chiamato [ICorDebugController:: continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) .</span><span class="sxs-lookup"><span data-stu-id="65b9b-110">Callbacks will be dispatched one at a time, each time [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) is called.</span></span> <span data-ttu-id="65b9b-111">Il debugger può verificare questo flag se desidera segnalare più eventi di debug che si verificano simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="65b9b-111">The debugger can check this flag if it wants to report multiple debugging events that occur simultaneously.</span></span>  
  
 <span data-ttu-id="65b9b-112">Quando gli eventi di debug sono accodati, si sono già verificati, pertanto il debugger deve svuotare l'intera coda per assicurarsi che lo stato dell'oggetto del debug.</span><span class="sxs-lookup"><span data-stu-id="65b9b-112">When debugging events are queued, they have already occurred, so the debugger must drain the entire queue to be sure of the state of the debuggee.</span></span> <span data-ttu-id="65b9b-113">Chiamare `ICorDebugController::Continue` per svuotare la coda. Se, ad esempio, la coda contiene due eventi di debug sul thread *x*e il debugger sospende il thread *x* dopo il primo evento di debug e quindi chiama `ICorDebugController::Continue`, il secondo evento di debug per il thread *x* verrà inviato anche se il il thread è stato sospeso.</span><span class="sxs-lookup"><span data-stu-id="65b9b-113">(Call `ICorDebugController::Continue` to drain the queue.) For example, if the queue contains two debugging events on thread *X*, and the debugger suspends thread *X* after the first debugging event and then calls `ICorDebugController::Continue`, the second debugging event for thread *X* will be dispatched although the thread has been suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65b9b-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="65b9b-114">Requirements</span></span>  
 <span data-ttu-id="65b9b-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65b9b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65b9b-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="65b9b-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="65b9b-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65b9b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65b9b-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65b9b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65b9b-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65b9b-119">See also</span></span>

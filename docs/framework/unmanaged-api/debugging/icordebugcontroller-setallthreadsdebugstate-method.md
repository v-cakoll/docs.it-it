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
ms.openlocfilehash: 1190f83e2671216cf1627eeb710ba576e4b2ec93
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125350"
---
# <a name="icordebugcontrollersetallthreadsdebugstate-method"></a><span data-ttu-id="50bb8-102">Metodo ICorDebugController::SetAllThreadsDebugState</span><span class="sxs-lookup"><span data-stu-id="50bb8-102">ICorDebugController::SetAllThreadsDebugState Method</span></span>
<span data-ttu-id="50bb8-103">Imposta lo stato di debug di tutti i thread gestiti nel processo.</span><span class="sxs-lookup"><span data-stu-id="50bb8-103">Sets the debug state of all managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50bb8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="50bb8-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAllThreadsDebugState (  
    [in] CorDebugThreadState  state,  
    [in] ICorDebugThread      *pExceptThisThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50bb8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="50bb8-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="50bb8-106">in Valore dell'enumerazione "CorDebugThreadState" che specifica lo stato del thread per il debug.</span><span class="sxs-lookup"><span data-stu-id="50bb8-106">[in] A value of the "CorDebugThreadState" enumeration that specifies the state of the thread for debugging.</span></span>  
  
 `pExceptThisThread`  
 <span data-ttu-id="50bb8-107">in Puntatore a un oggetto "ICorDebugThread" che rappresenta un thread da esentare dall'impostazione dello stato di debug.</span><span class="sxs-lookup"><span data-stu-id="50bb8-107">[in] A pointer to an "ICorDebugThread" object that represents a thread to be exempted from the debug state setting.</span></span> <span data-ttu-id="50bb8-108">Se questo valore è null, non viene esentato alcun thread.</span><span class="sxs-lookup"><span data-stu-id="50bb8-108">If this value is null, no thread is exempted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50bb8-109">Note</span><span class="sxs-lookup"><span data-stu-id="50bb8-109">Remarks</span></span>  
 <span data-ttu-id="50bb8-110">Il metodo `SetAllThreadsDebugState` può influire sui thread che non sono visibili tramite il [Metodo EnumerateThreads](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md), quindi i thread sospesi con il metodo di `SetAllThreadsDebugState` dovranno essere ripresi con il metodo `SetAllThreadsDebugState`.</span><span class="sxs-lookup"><span data-stu-id="50bb8-110">The `SetAllThreadsDebugState` method may affect threads that are not visible via [EnumerateThreads Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md), so threads that were suspended with the `SetAllThreadsDebugState` method will need to be resumed with the `SetAllThreadsDebugState` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50bb8-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="50bb8-111">Requirements</span></span>  
 <span data-ttu-id="50bb8-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50bb8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50bb8-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50bb8-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50bb8-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50bb8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50bb8-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50bb8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50bb8-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50bb8-116">See also</span></span>

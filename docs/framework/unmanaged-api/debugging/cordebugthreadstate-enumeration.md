---
title: Enumerazione CorDebugThreadState
ms.date: 03/30/2017
api_name:
- CorDebugThreadState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugThreadState
helpviewer_keywords:
- CorDebugThreadState enumeration [.NET Framework debugging]
ms.assetid: a3ccdf18-4ec6-494d-9024-48e5c8c724f5
topic_type:
- apiref
ms.openlocfilehash: 1ff36e8ef6b7c02eea5b02bc22587bc3889df093
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133701"
---
# <a name="cordebugthreadstate-enumeration"></a><span data-ttu-id="be77d-102">Enumerazione CorDebugThreadState</span><span class="sxs-lookup"><span data-stu-id="be77d-102">CorDebugThreadState Enumeration</span></span>
<span data-ttu-id="be77d-103">Specifica lo stato di un thread per il debug.</span><span class="sxs-lookup"><span data-stu-id="be77d-103">Specifies the state of a thread for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be77d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="be77d-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugThreadState {  
    THREAD_RUN,  
    THREAD_SUSPEND  
} CorDebugThreadState;  
```  
  
## <a name="members"></a><span data-ttu-id="be77d-105">Members</span><span class="sxs-lookup"><span data-stu-id="be77d-105">Members</span></span>  
  
|<span data-ttu-id="be77d-106">Member</span><span class="sxs-lookup"><span data-stu-id="be77d-106">Member</span></span>|<span data-ttu-id="be77d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="be77d-107">Description</span></span>|  
|------------|-----------------|  
|`THREAD_RUN`|<span data-ttu-id="be77d-108">Il thread viene eseguito liberamente, a meno che non si verifichi un evento di debug.</span><span class="sxs-lookup"><span data-stu-id="be77d-108">The thread runs freely, unless a debug event occurs.</span></span>|  
|`THREAD_SUSPEND`|<span data-ttu-id="be77d-109">Impossibile eseguire il thread.</span><span class="sxs-lookup"><span data-stu-id="be77d-109">The thread cannot run.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be77d-110">Note</span><span class="sxs-lookup"><span data-stu-id="be77d-110">Remarks</span></span>  
 <span data-ttu-id="be77d-111">Il debugger usa l'enumerazione `CorDebugThreadState` per controllare l'esecuzione di un thread.</span><span class="sxs-lookup"><span data-stu-id="be77d-111">The debugger uses the `CorDebugThreadState` enumeration to control a thread's execution.</span></span> <span data-ttu-id="be77d-112">Lo stato di un thread può essere impostato tramite il metodo [ICorDebugThread:: SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) o [ICorDebugController:: SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) .</span><span class="sxs-lookup"><span data-stu-id="be77d-112">The state of a thread can be set by using the [ICorDebugThread::SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) or [ICorDebugController::SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) method.</span></span>  
  
 <span data-ttu-id="be77d-113">Un callback fornito all' [API di hosting](../../../../docs/framework/unmanaged-api/hosting/index.md) consente il pumping dei messaggi, pertanto non è necessario uno stato interrotto.</span><span class="sxs-lookup"><span data-stu-id="be77d-113">A callback provided to the [hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md) enables message pumping, so an interrupted state is not needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be77d-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="be77d-114">Requirements</span></span>  
 <span data-ttu-id="be77d-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be77d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be77d-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="be77d-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="be77d-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be77d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be77d-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be77d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be77d-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be77d-119">See also</span></span>

- [<span data-ttu-id="be77d-120">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="be77d-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

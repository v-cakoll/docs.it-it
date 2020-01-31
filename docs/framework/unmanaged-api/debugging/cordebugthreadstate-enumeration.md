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
ms.openlocfilehash: 69a8aabd1d79bb9bb4248259c99124ce50677600
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789236"
---
# <a name="cordebugthreadstate-enumeration"></a><span data-ttu-id="8bb8b-102">Enumerazione CorDebugThreadState</span><span class="sxs-lookup"><span data-stu-id="8bb8b-102">CorDebugThreadState Enumeration</span></span>
<span data-ttu-id="8bb8b-103">Specifica lo stato di un thread per il debug.</span><span class="sxs-lookup"><span data-stu-id="8bb8b-103">Specifies the state of a thread for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bb8b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8bb8b-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugThreadState {  
    THREAD_RUN,  
    THREAD_SUSPEND  
} CorDebugThreadState;  
```  
  
## <a name="members"></a><span data-ttu-id="8bb8b-105">Membri</span><span class="sxs-lookup"><span data-stu-id="8bb8b-105">Members</span></span>  
  
|<span data-ttu-id="8bb8b-106">Member</span><span class="sxs-lookup"><span data-stu-id="8bb8b-106">Member</span></span>|<span data-ttu-id="8bb8b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8bb8b-107">Description</span></span>|  
|------------|-----------------|  
|`THREAD_RUN`|<span data-ttu-id="8bb8b-108">Il thread viene eseguito liberamente, a meno che non si verifichi un evento di debug.</span><span class="sxs-lookup"><span data-stu-id="8bb8b-108">The thread runs freely, unless a debug event occurs.</span></span>|  
|`THREAD_SUSPEND`|<span data-ttu-id="8bb8b-109">Impossibile eseguire il thread.</span><span class="sxs-lookup"><span data-stu-id="8bb8b-109">The thread cannot run.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8bb8b-110">Note</span><span class="sxs-lookup"><span data-stu-id="8bb8b-110">Remarks</span></span>  
 <span data-ttu-id="8bb8b-111">Il debugger usa l'enumerazione `CorDebugThreadState` per controllare l'esecuzione di un thread.</span><span class="sxs-lookup"><span data-stu-id="8bb8b-111">The debugger uses the `CorDebugThreadState` enumeration to control a thread's execution.</span></span> <span data-ttu-id="8bb8b-112">Lo stato di un thread può essere impostato tramite il metodo [ICorDebugThread:: SetDebugState](icordebugthread-setdebugstate-method.md) o [ICorDebugController:: SetAllThreadsDebugState](icordebugcontroller-setallthreadsdebugstate-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8bb8b-112">The state of a thread can be set by using the [ICorDebugThread::SetDebugState](icordebugthread-setdebugstate-method.md) or [ICorDebugController::SetAllThreadsDebugState](icordebugcontroller-setallthreadsdebugstate-method.md) method.</span></span>  
  
 <span data-ttu-id="8bb8b-113">Un callback fornito all' [API di hosting](../../../../docs/framework/unmanaged-api/hosting/index.md) consente il pumping dei messaggi, pertanto non è necessario uno stato interrotto.</span><span class="sxs-lookup"><span data-stu-id="8bb8b-113">A callback provided to the [hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md) enables message pumping, so an interrupted state is not needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bb8b-114">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="8bb8b-114">Requirements</span></span>  
 <span data-ttu-id="8bb8b-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8bb8b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bb8b-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8bb8b-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8bb8b-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8bb8b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8bb8b-118">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bb8b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bb8b-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8bb8b-119">See also</span></span>

- [<span data-ttu-id="8bb8b-120">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="8bb8b-120">Debugging Enumerations</span></span>](debugging-enumerations.md)

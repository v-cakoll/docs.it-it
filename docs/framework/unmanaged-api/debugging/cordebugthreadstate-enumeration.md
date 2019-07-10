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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce252f5a4b5fbcdbbc7b70c8b1c829490f8f63e5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739522"
---
# <a name="cordebugthreadstate-enumeration"></a><span data-ttu-id="2baa8-102">Enumerazione CorDebugThreadState</span><span class="sxs-lookup"><span data-stu-id="2baa8-102">CorDebugThreadState Enumeration</span></span>
<span data-ttu-id="2baa8-103">Specifica lo stato di un thread per il debug.</span><span class="sxs-lookup"><span data-stu-id="2baa8-103">Specifies the state of a thread for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2baa8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2baa8-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugThreadState {  
    THREAD_RUN,  
    THREAD_SUSPEND  
} CorDebugThreadState;  
```  
  
## <a name="members"></a><span data-ttu-id="2baa8-105">Membri</span><span class="sxs-lookup"><span data-stu-id="2baa8-105">Members</span></span>  
  
|<span data-ttu-id="2baa8-106">Member</span><span class="sxs-lookup"><span data-stu-id="2baa8-106">Member</span></span>|<span data-ttu-id="2baa8-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2baa8-107">Description</span></span>|  
|------------|-----------------|  
|`THREAD_RUN`|<span data-ttu-id="2baa8-108">Il thread esegue gratuitamente, a meno che non si verifica un evento di debug.</span><span class="sxs-lookup"><span data-stu-id="2baa8-108">The thread runs freely, unless a debug event occurs.</span></span>|  
|`THREAD_SUSPEND`|<span data-ttu-id="2baa8-109">Non è possibile eseguire il thread.</span><span class="sxs-lookup"><span data-stu-id="2baa8-109">The thread cannot run.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2baa8-110">Note</span><span class="sxs-lookup"><span data-stu-id="2baa8-110">Remarks</span></span>  
 <span data-ttu-id="2baa8-111">Il debugger usa il `CorDebugThreadState` enumerazione per controllare l'esecuzione di un thread.</span><span class="sxs-lookup"><span data-stu-id="2baa8-111">The debugger uses the `CorDebugThreadState` enumeration to control a thread's execution.</span></span> <span data-ttu-id="2baa8-112">Lo stato di un thread può essere impostato utilizzando il [SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) oppure [SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="2baa8-112">The state of a thread can be set by using the [ICorDebugThread::SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) or [ICorDebugController::SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) method.</span></span>  
  
 <span data-ttu-id="2baa8-113">Un callback fornito per il [API di hosting](../../../../docs/framework/unmanaged-api/hosting/index.md) consente la distribuzione dei messaggi, pertanto non è necessario uno stato interrotto.</span><span class="sxs-lookup"><span data-stu-id="2baa8-113">A callback provided to the [hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md) enables message pumping, so an interrupted state is not needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2baa8-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2baa8-114">Requirements</span></span>  
 <span data-ttu-id="2baa8-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2baa8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2baa8-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2baa8-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2baa8-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2baa8-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2baa8-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2baa8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2baa8-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2baa8-119">See also</span></span>

- [<span data-ttu-id="2baa8-120">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="2baa8-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

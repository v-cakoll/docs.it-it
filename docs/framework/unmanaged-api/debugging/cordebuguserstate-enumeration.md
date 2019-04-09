---
title: Enumerazione CorDebugUserState
ms.date: 03/30/2017
api_name:
- CorDebugUserState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUserState
helpviewer_keywords:
- CorDebugUserState enumeration [.NET Framework debugging]
ms.assetid: 5f6c2bcd-8102-4e3b-abc5-86ab0bd62def
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c54b2af6e7a200db89bfd7335868a629d7a886fc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141310"
---
# <a name="cordebuguserstate-enumeration"></a><span data-ttu-id="4d282-102">Enumerazione CorDebugUserState</span><span class="sxs-lookup"><span data-stu-id="4d282-102">CorDebugUserState Enumeration</span></span>
<span data-ttu-id="4d282-103">Indica lo stato utente di un thread.</span><span class="sxs-lookup"><span data-stu-id="4d282-103">Indicates the user state of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d282-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4d282-104">Syntax</span></span>  
  
```  
typedef enum CorDebugUserState {  
    USER_STOP_REQUESTED     =  0x01,  
    USER_SUSPEND_REQUESTED  =  0x02,  
    USER_BACKGROUND         =  0x04,  
    USER_UNSTARTED          =  0x08,  
    USER_STOPPED            =  0x10,  
    USER_WAIT_SLEEP_JOIN    =  0x20,  
    USER_SUSPENDED          =  0x40,  
    USER_UNSAFE_POINT       =  0x80,  
    USER_THREADPOOL         = 0x100  
} CorDebugUserState;  
```  
  
## <a name="members"></a><span data-ttu-id="4d282-105">Membri</span><span class="sxs-lookup"><span data-stu-id="4d282-105">Members</span></span>  
  
|<span data-ttu-id="4d282-106">Value</span><span class="sxs-lookup"><span data-stu-id="4d282-106">Value</span></span>|<span data-ttu-id="4d282-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d282-107">Description</span></span>|  
|-----------|-----------------|  
|`USER_STOP_REQUESTED`|<span data-ttu-id="4d282-108">È stata richiesta la terminazione del thread.</span><span class="sxs-lookup"><span data-stu-id="4d282-108">A termination of the thread has been requested.</span></span>|  
|`USER_SUSPEND_REQUESTED`|<span data-ttu-id="4d282-109">È stata richiesta una sospensione del thread.</span><span class="sxs-lookup"><span data-stu-id="4d282-109">A suspension of the thread has been requested.</span></span>|  
|`USER_BACKGROUND`|<span data-ttu-id="4d282-110">Il thread è in esecuzione in background.</span><span class="sxs-lookup"><span data-stu-id="4d282-110">The thread is running in the background.</span></span>|  
|`USER_UNSTARTED`|<span data-ttu-id="4d282-111">Il thread non ha avviato l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4d282-111">The thread has not started executing.</span></span>|  
|`USER_STOPPED`|<span data-ttu-id="4d282-112">Il thread è stato terminato.</span><span class="sxs-lookup"><span data-stu-id="4d282-112">The thread has been terminated.</span></span>|  
|`USER_WAIT_SLEEP_JOIN`|<span data-ttu-id="4d282-113">Il thread è in attesa di un altro thread completare un'attività.</span><span class="sxs-lookup"><span data-stu-id="4d282-113">The thread is waiting for another thread to complete a task.</span></span>|  
|`USER_SUSPENDED`|<span data-ttu-id="4d282-114">Il thread è stato sospeso.</span><span class="sxs-lookup"><span data-stu-id="4d282-114">The thread has been suspended.</span></span>|  
|`USER_UNSAFE_POINT`|<span data-ttu-id="4d282-115">Il thread è in un punto non sicuro.</span><span class="sxs-lookup"><span data-stu-id="4d282-115">The thread is at an unsafe point.</span></span> <span data-ttu-id="4d282-116">Vale a dire, il thread è in un punto nell'esecuzione in cui potrebbe bloccare l'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="4d282-116">That is, the thread is at a point in execution where it may block garbage collection.</span></span><br /><br /> <span data-ttu-id="4d282-117">Eseguire il debug gli eventi possono essere inviati dai punti di tipo unsafe, ma la sospensione di un thread in un punto dell'unsafe molto probabilmente provocherà un deadlock finché non viene ripreso il thread.</span><span class="sxs-lookup"><span data-stu-id="4d282-117">Debug events may be dispatched from unsafe points, but suspending a thread at an unsafe point  will very likely cause a deadlock until the thread is resumed.</span></span> <span data-ttu-id="4d282-118">I punti sicuri e sono determinati dalla just-in-time (JIT) e dall'implementazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="4d282-118">The safe and unsafe points are determined by the just-in-time (JIT) and garbage collection implementation.</span></span>|  
|`USER_THREADPOOL`|<span data-ttu-id="4d282-119">Il thread è il pool di thread.</span><span class="sxs-lookup"><span data-stu-id="4d282-119">The thread is from the thread pool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d282-120">Note</span><span class="sxs-lookup"><span data-stu-id="4d282-120">Remarks</span></span>  
 <span data-ttu-id="4d282-121">Lo stato utente di un thread è lo stato in cui il thread ha quando lo esamina il debugger.</span><span class="sxs-lookup"><span data-stu-id="4d282-121">The user state of a thread is the state that the thread has when the debugger examines it.</span></span> <span data-ttu-id="4d282-122">Un thread può avere una combinazione di stati utente.</span><span class="sxs-lookup"><span data-stu-id="4d282-122">A thread may have a combination of user states.</span></span>  
  
 <span data-ttu-id="4d282-123">Usare la [GetUserState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md) metodo per recuperare lo stato utente del thread.</span><span class="sxs-lookup"><span data-stu-id="4d282-123">Use the [ICorDebugThread::GetUserState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md) method to retrieve a thread's user state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d282-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4d282-124">Requirements</span></span>  
 <span data-ttu-id="4d282-125">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d282-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d282-126">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4d282-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d282-127">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d282-127">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="4d282-128">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="4d282-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4d282-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d282-129">See also</span></span>

- [<span data-ttu-id="4d282-130">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="4d282-130">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

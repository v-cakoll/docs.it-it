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
ms.openlocfilehash: d502b4098016fb14793bccd6feb641e92e3c2611
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795638"
---
# <a name="cordebuguserstate-enumeration"></a><span data-ttu-id="02d43-102">Enumerazione CorDebugUserState</span><span class="sxs-lookup"><span data-stu-id="02d43-102">CorDebugUserState Enumeration</span></span>
<span data-ttu-id="02d43-103">Indica lo stato utente di un thread.</span><span class="sxs-lookup"><span data-stu-id="02d43-103">Indicates the user state of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02d43-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="02d43-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="02d43-105">Members</span><span class="sxs-lookup"><span data-stu-id="02d43-105">Members</span></span>  
  
|<span data-ttu-id="02d43-106">Valore</span><span class="sxs-lookup"><span data-stu-id="02d43-106">Value</span></span>|<span data-ttu-id="02d43-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02d43-107">Description</span></span>|  
|-----------|-----------------|  
|`USER_STOP_REQUESTED`|<span data-ttu-id="02d43-108">È stata richiesta una terminazione del thread.</span><span class="sxs-lookup"><span data-stu-id="02d43-108">A termination of the thread has been requested.</span></span>|  
|`USER_SUSPEND_REQUESTED`|<span data-ttu-id="02d43-109">È stata richiesta una sospensione del thread.</span><span class="sxs-lookup"><span data-stu-id="02d43-109">A suspension of the thread has been requested.</span></span>|  
|`USER_BACKGROUND`|<span data-ttu-id="02d43-110">Il thread è in esecuzione in background.</span><span class="sxs-lookup"><span data-stu-id="02d43-110">The thread is running in the background.</span></span>|  
|`USER_UNSTARTED`|<span data-ttu-id="02d43-111">L'esecuzione del thread non è stata avviata.</span><span class="sxs-lookup"><span data-stu-id="02d43-111">The thread has not started executing.</span></span>|  
|`USER_STOPPED`|<span data-ttu-id="02d43-112">Il thread è stato terminato.</span><span class="sxs-lookup"><span data-stu-id="02d43-112">The thread has been terminated.</span></span>|  
|`USER_WAIT_SLEEP_JOIN`|<span data-ttu-id="02d43-113">Il thread è in attesa del completamento di un'attività da parte di un altro thread.</span><span class="sxs-lookup"><span data-stu-id="02d43-113">The thread is waiting for another thread to complete a task.</span></span>|  
|`USER_SUSPENDED`|<span data-ttu-id="02d43-114">Il thread è stato sospeso.</span><span class="sxs-lookup"><span data-stu-id="02d43-114">The thread has been suspended.</span></span>|  
|`USER_UNSAFE_POINT`|<span data-ttu-id="02d43-115">Il thread si trova in un punto non sicuro.</span><span class="sxs-lookup"><span data-stu-id="02d43-115">The thread is at an unsafe point.</span></span> <span data-ttu-id="02d43-116">Ovvero, il thread si trova in un punto di esecuzione in cui può bloccare Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="02d43-116">That is, the thread is at a point in execution where it may block garbage collection.</span></span><br /><br /> <span data-ttu-id="02d43-117">Gli eventi di debug possono essere inviati da punti unsafe, ma la sospensione di un thread in un punto non sicuro provocherà molto probabilmente un deadlock finché il thread non verrà ripreso.</span><span class="sxs-lookup"><span data-stu-id="02d43-117">Debug events may be dispatched from unsafe points, but suspending a thread at an unsafe point  will very likely cause a deadlock until the thread is resumed.</span></span> <span data-ttu-id="02d43-118">I punti safe e unsafe sono determinati dall'implementazione JIT (just-in-Time) e Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="02d43-118">The safe and unsafe points are determined by the just-in-time (JIT) and garbage collection implementation.</span></span>|  
|`USER_THREADPOOL`|<span data-ttu-id="02d43-119">Il thread viene dal pool di thread.</span><span class="sxs-lookup"><span data-stu-id="02d43-119">The thread is from the thread pool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02d43-120">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="02d43-120">Remarks</span></span>  
 <span data-ttu-id="02d43-121">Lo stato utente di un thread è lo stato che il thread ha quando viene esaminato dal debugger.</span><span class="sxs-lookup"><span data-stu-id="02d43-121">The user state of a thread is the state that the thread has when the debugger examines it.</span></span> <span data-ttu-id="02d43-122">Un thread può avere una combinazione di stati utente.</span><span class="sxs-lookup"><span data-stu-id="02d43-122">A thread may have a combination of user states.</span></span>  
  
 <span data-ttu-id="02d43-123">Usare il metodo [ICorDebugThread:: GetUserState](icordebugthread-getuserstate-method.md) per recuperare lo stato utente di un thread.</span><span class="sxs-lookup"><span data-stu-id="02d43-123">Use the [ICorDebugThread::GetUserState](icordebugthread-getuserstate-method.md) method to retrieve a thread's user state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02d43-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="02d43-124">Requirements</span></span>  
 <span data-ttu-id="02d43-125">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02d43-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02d43-126">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="02d43-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02d43-127">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02d43-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02d43-128">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02d43-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02d43-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02d43-129">See also</span></span>

- [<span data-ttu-id="02d43-130">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="02d43-130">Debugging Enumerations</span></span>](debugging-enumerations.md)

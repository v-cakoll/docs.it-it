---
title: Enumerazione CorDebugUserState
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 57fd9df27b1911c90bd11712b67e6e64588c2b5f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="cordebuguserstate-enumeration"></a><span data-ttu-id="bc0ff-102">Enumerazione CorDebugUserState</span><span class="sxs-lookup"><span data-stu-id="bc0ff-102">CorDebugUserState Enumeration</span></span>
<span data-ttu-id="bc0ff-103">Indica lo stato utente di un thread.</span><span class="sxs-lookup"><span data-stu-id="bc0ff-103">Indicates the user state of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc0ff-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bc0ff-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="bc0ff-105">Membri</span><span class="sxs-lookup"><span data-stu-id="bc0ff-105">Members</span></span>  
  
|<span data-ttu-id="bc0ff-106">Valore</span><span class="sxs-lookup"><span data-stu-id="bc0ff-106">Value</span></span>|<span data-ttu-id="bc0ff-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bc0ff-107">Description</span></span>|  
|-----------|-----------------|  
|`USER_STOP_REQUESTED`|<span data-ttu-id="bc0ff-108">È stata richiesta la terminazione del thread.</span><span class="sxs-lookup"><span data-stu-id="bc0ff-108">A termination of the thread has been requested.</span></span>|  
|`USER_SUSPEND_REQUESTED`|<span data-ttu-id="bc0ff-109">È stata richiesta una sospensione del thread.</span><span class="sxs-lookup"><span data-stu-id="bc0ff-109">A suspension of the thread has been requested.</span></span>|  
|`USER_BACKGROUND`|<span data-ttu-id="bc0ff-110">Il thread è in esecuzione in background.</span><span class="sxs-lookup"><span data-stu-id="bc0ff-110">The thread is running in the background.</span></span>|  
|`USER_UNSTARTED`|<span data-ttu-id="bc0ff-111">Il thread non ha avviato l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="bc0ff-111">The thread has not started executing.</span></span>|  
|`USER_STOPPED`|<span data-ttu-id="bc0ff-112">Il thread è stato terminato.</span><span class="sxs-lookup"><span data-stu-id="bc0ff-112">The thread has been terminated.</span></span>|  
|`USER_WAIT_SLEEP_JOIN`|<span data-ttu-id="bc0ff-113">Il thread è in attesa di un altro thread completare un'attività.</span><span class="sxs-lookup"><span data-stu-id="bc0ff-113">The thread is waiting for another thread to complete a task.</span></span>|  
|`USER_SUSPENDED`|<span data-ttu-id="bc0ff-114">Il thread è stata sospesa.</span><span class="sxs-lookup"><span data-stu-id="bc0ff-114">The thread has been suspended.</span></span>|  
|`USER_UNSAFE_POINT`|<span data-ttu-id="bc0ff-115">Il thread è in un punto unsafe.</span><span class="sxs-lookup"><span data-stu-id="bc0ff-115">The thread is at an unsafe point.</span></span> <span data-ttu-id="bc0ff-116">Il thread è in esecuzione un punto in cui potrebbe bloccare l'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="bc0ff-116">That is, the thread is at a point in execution where it may block garbage collection.</span></span><br /><br /> <span data-ttu-id="bc0ff-117">Eseguire il debug sia possibile inviare eventi da punti non sicuri, ma la sospensione di un thread in un punto unsafe molto probabile che un deadlock fino alla ripresa del thread.</span><span class="sxs-lookup"><span data-stu-id="bc0ff-117">Debug events may be dispatched from unsafe points, but suspending a thread at an unsafe point  will very likely cause a deadlock until the thread is resumed.</span></span> <span data-ttu-id="bc0ff-118">I punti sicuri e sono determinati dal just-in-time (JIT) e implementazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="bc0ff-118">The safe and unsafe points are determined by the just-in-time (JIT) and garbage collection implementation.</span></span>|  
|`USER_THREADPOOL`|<span data-ttu-id="bc0ff-119">Il thread è dal pool di thread.</span><span class="sxs-lookup"><span data-stu-id="bc0ff-119">The thread is from the thread pool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc0ff-120">Note</span><span class="sxs-lookup"><span data-stu-id="bc0ff-120">Remarks</span></span>  
 <span data-ttu-id="bc0ff-121">Lo stato utente di un thread è lo stato in cui il thread è presente quando si esamina il debugger.</span><span class="sxs-lookup"><span data-stu-id="bc0ff-121">The user state of a thread is the state that the thread has when the debugger examines it.</span></span> <span data-ttu-id="bc0ff-122">Un thread può avere una combinazione di stati utente.</span><span class="sxs-lookup"><span data-stu-id="bc0ff-122">A thread may have a combination of user states.</span></span>  
  
 <span data-ttu-id="bc0ff-123">Utilizzare il [GetUserState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md) metodo per recuperare lo stato utente di un thread.</span><span class="sxs-lookup"><span data-stu-id="bc0ff-123">Use the [ICorDebugThread::GetUserState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md) method to retrieve a thread's user state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc0ff-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bc0ff-124">Requirements</span></span>  
 <span data-ttu-id="bc0ff-125">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc0ff-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc0ff-126">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="bc0ff-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bc0ff-127">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc0ff-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc0ff-128">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc0ff-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc0ff-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc0ff-129">See Also</span></span>  
 [<span data-ttu-id="bc0ff-130">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="bc0ff-130">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

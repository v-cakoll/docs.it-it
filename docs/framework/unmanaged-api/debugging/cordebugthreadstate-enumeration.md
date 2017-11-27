---
title: Enumerazione CorDebugThreadState
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugThreadState
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugThreadState
helpviewer_keywords: CorDebugThreadState enumeration [.NET Framework debugging]
ms.assetid: a3ccdf18-4ec6-494d-9024-48e5c8c724f5
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dc3555d0ecd85208688a4aae69aef7c6c88303b3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugthreadstate-enumeration"></a><span data-ttu-id="29155-102">Enumerazione CorDebugThreadState</span><span class="sxs-lookup"><span data-stu-id="29155-102">CorDebugThreadState Enumeration</span></span>
<span data-ttu-id="29155-103">Specifica lo stato di un thread per il debug.</span><span class="sxs-lookup"><span data-stu-id="29155-103">Specifies the state of a thread for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29155-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="29155-104">Syntax</span></span>  
  
```  
typedef enum CorDebugThreadState {  
    THREAD_RUN,  
    THREAD_SUSPEND  
} CorDebugThreadState;  
```  
  
## <a name="members"></a><span data-ttu-id="29155-105">Membri</span><span class="sxs-lookup"><span data-stu-id="29155-105">Members</span></span>  
  
|<span data-ttu-id="29155-106">Membro</span><span class="sxs-lookup"><span data-stu-id="29155-106">Member</span></span>|<span data-ttu-id="29155-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="29155-107">Description</span></span>|  
|------------|-----------------|  
|`THREAD_RUN`|<span data-ttu-id="29155-108">Il thread viene eseguito liberamente, a meno che non si verifica un evento di debug.</span><span class="sxs-lookup"><span data-stu-id="29155-108">The thread runs freely, unless a debug event occurs.</span></span>|  
|`THREAD_SUSPEND`|<span data-ttu-id="29155-109">Impossibile eseguire il thread.</span><span class="sxs-lookup"><span data-stu-id="29155-109">The thread cannot run.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29155-110">Note</span><span class="sxs-lookup"><span data-stu-id="29155-110">Remarks</span></span>  
 <span data-ttu-id="29155-111">Il debugger usa il `CorDebugThreadState` enumerazione per controllare l'esecuzione di un thread.</span><span class="sxs-lookup"><span data-stu-id="29155-111">The debugger uses the `CorDebugThreadState` enumeration to control a thread's execution.</span></span> <span data-ttu-id="29155-112">Lo stato di un thread può essere impostato utilizzando il [ICorDebugThread:: SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) o [ICorDebugController:: SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="29155-112">The state of a thread can be set by using the [ICorDebugThread::SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) or [ICorDebugController::SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) method.</span></span>  
  
 <span data-ttu-id="29155-113">Un callback fornito per il [API di hosting](../../../../docs/framework/unmanaged-api/hosting/index.md) consente la distribuzione dei messaggi, pertanto non è necessario uno stato interrotto.</span><span class="sxs-lookup"><span data-stu-id="29155-113">A callback provided to the [hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md) enables message pumping, so an interrupted state is not needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29155-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="29155-114">Requirements</span></span>  
 <span data-ttu-id="29155-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29155-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29155-116">**Intestazione:** CorDebug.idl, CorDegug.h</span><span class="sxs-lookup"><span data-stu-id="29155-116">**Header:** CorDebug.idl, CorDegug.h</span></span>  
  
 <span data-ttu-id="29155-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29155-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29155-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29155-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29155-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29155-119">See Also</span></span>  
 [<span data-ttu-id="29155-120">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="29155-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

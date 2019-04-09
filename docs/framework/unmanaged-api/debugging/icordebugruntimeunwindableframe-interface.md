---
title: Interfaccia ICorDebugRuntimeUnwindableFrame
ms.date: 03/30/2017
api_name:
- ICorDebugUnwindableFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnwindableFrame
helpviewer_keywords:
- ICorDebugUnwindableFrame interface [.NET Framework debugging]
ms.assetid: cd6a3982-6ed3-4909-808d-a66055e813e0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf6bc73683a6c37ceaaffc635a58803b71c3b6cd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134199"
---
# <a name="icordebugruntimeunwindableframe-interface"></a><span data-ttu-id="7a600-102">Interfaccia ICorDebugRuntimeUnwindableFrame</span><span class="sxs-lookup"><span data-stu-id="7a600-102">ICorDebugRuntimeUnwindableFrame Interface</span></span>
<span data-ttu-id="7a600-103">Fornisce supporto per i metodi non gestiti che richiedono a Common Language Runtime (CLR) di rimuovere un frame.</span><span class="sxs-lookup"><span data-stu-id="7a600-103">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a600-104">Note</span><span class="sxs-lookup"><span data-stu-id="7a600-104">Remarks</span></span>  
 `ICorDebugRuntimeUnwindableFrame` <span data-ttu-id="7a600-105">è una versione particolare dell'interfaccia ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="7a600-105">is a specialized version of the ICorDebugFrame interface.</span></span> <span data-ttu-id="7a600-106">Viene usato dai metodi non gestiti che richiedono il runtime di rimuovere un frame sullo stack corrente.</span><span class="sxs-lookup"><span data-stu-id="7a600-106">It is used by unmanaged methods that require the runtime to unwind a frame on the current stack.</span></span> <span data-ttu-id="7a600-107">Convenzioni di rimozione esistenti non funzionano, perché non utilizzare codice con compilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="7a600-107">Existing unwinding conventions do not work, because they do not use JIT-compiled code.</span></span> <span data-ttu-id="7a600-108">Quando il debugger rileva un frame non, consigliabile usare la [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) metodo per la rimozione, ma deve eseguire l'ispezione stesso.</span><span class="sxs-lookup"><span data-stu-id="7a600-108">When the debugger sees an unwindable frame, it should use the [ICorDebugStackWalk::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) method to unwind it, but it should perform inspection itself.</span></span> <span data-ttu-id="7a600-109">Quando il debugger riceve un' `ICorDebugRuntimeUnwindableFrame`, può chiamare le [ICorDebugStackWalk:: GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) metodo per recuperare il contesto del frame.</span><span class="sxs-lookup"><span data-stu-id="7a600-109">When the debugger receives an `ICorDebugRuntimeUnwindableFrame`, it can call the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method to retrieve the context of the frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a600-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7a600-110">Requirements</span></span>  
 <span data-ttu-id="7a600-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a600-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a600-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7a600-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7a600-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a600-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="7a600-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="7a600-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7a600-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a600-115">See also</span></span>

- [<span data-ttu-id="7a600-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="7a600-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="7a600-117">Debug</span><span class="sxs-lookup"><span data-stu-id="7a600-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

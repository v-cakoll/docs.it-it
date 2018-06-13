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
ms.openlocfilehash: 3e2edc64cd9067ed89ae0e309c6a5630319ce835
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420599"
---
# <a name="icordebugruntimeunwindableframe-interface"></a><span data-ttu-id="6bb15-102">Interfaccia ICorDebugRuntimeUnwindableFrame</span><span class="sxs-lookup"><span data-stu-id="6bb15-102">ICorDebugRuntimeUnwindableFrame Interface</span></span>
<span data-ttu-id="6bb15-103">Fornisce supporto per i metodi non gestiti che richiedono a Common Language Runtime (CLR) di rimuovere un frame.</span><span class="sxs-lookup"><span data-stu-id="6bb15-103">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6bb15-104">Note</span><span class="sxs-lookup"><span data-stu-id="6bb15-104">Remarks</span></span>  
 <span data-ttu-id="6bb15-105">`ICorDebugRuntimeUnwindableFrame` è una versione specializzata di ICorDebugFrame (interfaccia).</span><span class="sxs-lookup"><span data-stu-id="6bb15-105">`ICorDebugRuntimeUnwindableFrame` is a specialized version of the ICorDebugFrame interface.</span></span> <span data-ttu-id="6bb15-106">Viene utilizzato dai metodi non gestiti che richiedono il runtime di rimuovere un frame sullo stack corrente.</span><span class="sxs-lookup"><span data-stu-id="6bb15-106">It is used by unmanaged methods that require the runtime to unwind a frame on the current stack.</span></span> <span data-ttu-id="6bb15-107">Convenzioni di rimozione esistenti non funzionano, poiché non utilizzano codice con compilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="6bb15-107">Existing unwinding conventions do not work, because they do not use JIT-compiled code.</span></span> <span data-ttu-id="6bb15-108">Quando il debugger rileva un frame non, è necessario utilizzare il [ICorDebugStackWalk:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) metodo per la rimozione, ma si deve eseguire l'ispezione stesso.</span><span class="sxs-lookup"><span data-stu-id="6bb15-108">When the debugger sees an unwindable frame, it should use the [ICorDebugStackWalk::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) method to unwind it, but it should perform inspection itself.</span></span> <span data-ttu-id="6bb15-109">Quando il debugger riceve un `ICorDebugRuntimeUnwindableFrame`, può chiamare il [ICorDebugStackWalk::](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) metodo per recuperare il contesto del frame.</span><span class="sxs-lookup"><span data-stu-id="6bb15-109">When the debugger receives an `ICorDebugRuntimeUnwindableFrame`, it can call the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method to retrieve the context of the frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bb15-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6bb15-110">Requirements</span></span>  
 <span data-ttu-id="6bb15-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6bb15-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bb15-112">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="6bb15-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6bb15-113">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="6bb15-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6bb15-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bb15-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bb15-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6bb15-115">See Also</span></span>  
 [<span data-ttu-id="6bb15-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="6bb15-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="6bb15-117">Debug</span><span class="sxs-lookup"><span data-stu-id="6bb15-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

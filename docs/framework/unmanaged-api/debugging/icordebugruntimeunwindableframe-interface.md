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
ms.openlocfilehash: 26b0c78d5b34b920decc8c549d90ba8147e3f323
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791926"
---
# <a name="icordebugruntimeunwindableframe-interface"></a><span data-ttu-id="b17d3-102">Interfaccia ICorDebugRuntimeUnwindableFrame</span><span class="sxs-lookup"><span data-stu-id="b17d3-102">ICorDebugRuntimeUnwindableFrame Interface</span></span>
<span data-ttu-id="b17d3-103">Fornisce supporto per i metodi non gestiti che richiedono a Common Language Runtime (CLR) di rimuovere un frame.</span><span class="sxs-lookup"><span data-stu-id="b17d3-103">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b17d3-104">Note</span><span class="sxs-lookup"><span data-stu-id="b17d3-104">Remarks</span></span>  
 <span data-ttu-id="b17d3-105">`ICorDebugRuntimeUnwindableFrame` è una versione specializzata dell'interfaccia ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="b17d3-105">`ICorDebugRuntimeUnwindableFrame` is a specialized version of the ICorDebugFrame interface.</span></span> <span data-ttu-id="b17d3-106">Viene usato da metodi non gestiti che richiedono al runtime di rimuovere un frame nello stack corrente.</span><span class="sxs-lookup"><span data-stu-id="b17d3-106">It is used by unmanaged methods that require the runtime to unwind a frame on the current stack.</span></span> <span data-ttu-id="b17d3-107">Le convenzioni di rimozione esistenti non funzionano perché non utilizzano codice compilato tramite JIT.</span><span class="sxs-lookup"><span data-stu-id="b17d3-107">Existing unwinding conventions do not work, because they do not use JIT-compiled code.</span></span> <span data-ttu-id="b17d3-108">Quando il debugger rileva un frame non ricaricabile, deve usare il metodo [ICorDebugStackWalk:: Next](icordebugstackwalk-next-method.md) per rimuoverlo, ma deve eseguire un controllo.</span><span class="sxs-lookup"><span data-stu-id="b17d3-108">When the debugger sees an unwindable frame, it should use the [ICorDebugStackWalk::Next](icordebugstackwalk-next-method.md) method to unwind it, but it should perform inspection itself.</span></span> <span data-ttu-id="b17d3-109">Quando il debugger riceve una `ICorDebugRuntimeUnwindableFrame`, può chiamare il metodo [ICorDebugStackWalk:: GetContext](icordebugstackwalk-getcontext-method.md) per recuperare il contesto del frame.</span><span class="sxs-lookup"><span data-stu-id="b17d3-109">When the debugger receives an `ICorDebugRuntimeUnwindableFrame`, it can call the [ICorDebugStackWalk::GetContext](icordebugstackwalk-getcontext-method.md) method to retrieve the context of the frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b17d3-110">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="b17d3-110">Requirements</span></span>  
 <span data-ttu-id="b17d3-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b17d3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b17d3-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b17d3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b17d3-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b17d3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b17d3-114">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b17d3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b17d3-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b17d3-115">See also</span></span>

- [<span data-ttu-id="b17d3-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="b17d3-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="b17d3-117">Debug</span><span class="sxs-lookup"><span data-stu-id="b17d3-117">Debugging</span></span>](index.md)

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
ms.openlocfilehash: a7b0608e85411844828cebea34c0ce5ef5b1bd11
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379390"
---
# <a name="icordebugruntimeunwindableframe-interface"></a><span data-ttu-id="48d84-102">Interfaccia ICorDebugRuntimeUnwindableFrame</span><span class="sxs-lookup"><span data-stu-id="48d84-102">ICorDebugRuntimeUnwindableFrame Interface</span></span>
<span data-ttu-id="48d84-103">Fornisce supporto per i metodi non gestiti che richiedono a Common Language Runtime (CLR) di rimuovere un frame.</span><span class="sxs-lookup"><span data-stu-id="48d84-103">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48d84-104">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="48d84-104">Remarks</span></span>  
 <span data-ttu-id="48d84-105">`ICorDebugRuntimeUnwindableFrame`è una versione specializzata dell'interfaccia ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="48d84-105">`ICorDebugRuntimeUnwindableFrame` is a specialized version of the ICorDebugFrame interface.</span></span> <span data-ttu-id="48d84-106">Viene usato da metodi non gestiti che richiedono al runtime di rimuovere un frame nello stack corrente.</span><span class="sxs-lookup"><span data-stu-id="48d84-106">It is used by unmanaged methods that require the runtime to unwind a frame on the current stack.</span></span> <span data-ttu-id="48d84-107">Le convenzioni di rimozione esistenti non funzionano perché non utilizzano codice compilato tramite JIT.</span><span class="sxs-lookup"><span data-stu-id="48d84-107">Existing unwinding conventions do not work, because they do not use JIT-compiled code.</span></span> <span data-ttu-id="48d84-108">Quando il debugger rileva un frame non ricaricabile, deve usare il metodo [ICorDebugStackWalk:: Next](icordebugstackwalk-next-method.md) per rimuoverlo, ma deve eseguire un controllo.</span><span class="sxs-lookup"><span data-stu-id="48d84-108">When the debugger sees an unwindable frame, it should use the [ICorDebugStackWalk::Next](icordebugstackwalk-next-method.md) method to unwind it, but it should perform inspection itself.</span></span> <span data-ttu-id="48d84-109">Quando il debugger riceve un oggetto `ICorDebugRuntimeUnwindableFrame` , può chiamare il metodo [ICorDebugStackWalk:: GetContext](icordebugstackwalk-getcontext-method.md) per recuperare il contesto del frame.</span><span class="sxs-lookup"><span data-stu-id="48d84-109">When the debugger receives an `ICorDebugRuntimeUnwindableFrame`, it can call the [ICorDebugStackWalk::GetContext](icordebugstackwalk-getcontext-method.md) method to retrieve the context of the frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48d84-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="48d84-110">Requirements</span></span>  
 <span data-ttu-id="48d84-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48d84-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48d84-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="48d84-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48d84-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48d84-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48d84-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48d84-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48d84-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48d84-115">See also</span></span>

- [<span data-ttu-id="48d84-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="48d84-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="48d84-117">Debug</span><span class="sxs-lookup"><span data-stu-id="48d84-117">Debugging</span></span>](index.md)

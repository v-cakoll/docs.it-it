---
title: Interfaccia ICorDebugVirtualUnwinder
ms.date: 03/30/2017
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9db6b83e2feedd761b95dec455213051e37366e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54684145"
---
# <a name="icordebugvirtualunwinder-interface"></a><span data-ttu-id="d406c-102">Interfaccia ICorDebugVirtualUnwinder</span><span class="sxs-lookup"><span data-stu-id="d406c-102">ICorDebugVirtualUnwinder Interface</span></span>
<span data-ttu-id="d406c-103">Fornisce metodi che facilitano lo svuotamento dello stack.</span><span class="sxs-lookup"><span data-stu-id="d406c-103">Provides methods to help in stack unwinding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d406c-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="d406c-104">Methods</span></span>  
  
|<span data-ttu-id="d406c-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="d406c-105">Method</span></span>|<span data-ttu-id="d406c-106">nome</span><span class="sxs-lookup"><span data-stu-id="d406c-106">Name</span></span>|  
|------------|----------|  
|[<span data-ttu-id="d406c-107">Metodo GetContext</span><span class="sxs-lookup"><span data-stu-id="d406c-107">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-getcontext-method.md)|<span data-ttu-id="d406c-108">Ottiene il contesto corrente di questo agente di rimozione.</span><span class="sxs-lookup"><span data-stu-id="d406c-108">Gets the current context of this unwinder.</span></span>|  
|[<span data-ttu-id="d406c-109">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="d406c-109">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-next-method.md)|<span data-ttu-id="d406c-110">Avanza fino al contesto del chiamante.</span><span class="sxs-lookup"><span data-stu-id="d406c-110">Advances to the caller's context.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d406c-111">Note</span><span class="sxs-lookup"><span data-stu-id="d406c-111">Remarks</span></span>  
 <span data-ttu-id="d406c-112">I membri dell'interfaccia `ICorDebugVirtualUnwinder` sono implementati dal debugger per agevolare lo svuotamento dello stack.</span><span class="sxs-lookup"><span data-stu-id="d406c-112">The members of the `ICorDebugVirtualUnwinder` interface are implemented by the debugger to help in stack unwinding.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d406c-113">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d406c-113">This interface is available with .NET Native only.</span></span> <span data-ttu-id="d406c-114">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="d406c-114">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d406c-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d406c-115">Requirements</span></span>  
 <span data-ttu-id="d406c-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d406c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d406c-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d406c-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d406c-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d406c-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d406c-119">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d406c-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d406c-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d406c-120">See also</span></span>
- [<span data-ttu-id="d406c-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="d406c-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="d406c-122">Debug</span><span class="sxs-lookup"><span data-stu-id="d406c-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

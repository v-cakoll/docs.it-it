---
title: Interfaccia ICorDebugVirtualUnwinder
ms.date: 03/30/2017
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bb04ac42b3cc77db3af53c87efb0d1f1f75da928
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421285"
---
# <a name="icordebugvirtualunwinder-interface"></a><span data-ttu-id="fe4f5-102">Interfaccia ICorDebugVirtualUnwinder</span><span class="sxs-lookup"><span data-stu-id="fe4f5-102">ICorDebugVirtualUnwinder Interface</span></span>
<span data-ttu-id="fe4f5-103">Fornisce metodi che facilitano lo svuotamento dello stack.</span><span class="sxs-lookup"><span data-stu-id="fe4f5-103">Provides methods to help in stack unwinding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fe4f5-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="fe4f5-104">Methods</span></span>  
  
|<span data-ttu-id="fe4f5-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="fe4f5-105">Method</span></span>|<span data-ttu-id="fe4f5-106">nome</span><span class="sxs-lookup"><span data-stu-id="fe4f5-106">Name</span></span>|  
|------------|----------|  
|[<span data-ttu-id="fe4f5-107">Metodo GetContext</span><span class="sxs-lookup"><span data-stu-id="fe4f5-107">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-getcontext-method.md)|<span data-ttu-id="fe4f5-108">Ottiene il contesto corrente di questo agente di rimozione.</span><span class="sxs-lookup"><span data-stu-id="fe4f5-108">Gets the current context of this unwinder.</span></span>|  
|[<span data-ttu-id="fe4f5-109">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="fe4f5-109">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-next-method.md)|<span data-ttu-id="fe4f5-110">Avanza fino al contesto del chiamante.</span><span class="sxs-lookup"><span data-stu-id="fe4f5-110">Advances to the caller's context.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe4f5-111">Note</span><span class="sxs-lookup"><span data-stu-id="fe4f5-111">Remarks</span></span>  
 <span data-ttu-id="fe4f5-112">I membri dell'interfaccia `ICorDebugVirtualUnwinder` sono implementati dal debugger per agevolare lo svuotamento dello stack.</span><span class="sxs-lookup"><span data-stu-id="fe4f5-112">The members of the `ICorDebugVirtualUnwinder` interface are implemented by the debugger to help in stack unwinding.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe4f5-113">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="fe4f5-113">This interface is available with .NET Native only.</span></span> <span data-ttu-id="fe4f5-114">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="fe4f5-114">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe4f5-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fe4f5-115">Requirements</span></span>  
 <span data-ttu-id="fe4f5-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe4f5-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe4f5-117">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="fe4f5-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe4f5-118">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="fe4f5-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe4f5-119">**Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe4f5-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe4f5-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe4f5-120">See Also</span></span>  
 [<span data-ttu-id="fe4f5-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="fe4f5-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="fe4f5-122">Debug</span><span class="sxs-lookup"><span data-stu-id="fe4f5-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

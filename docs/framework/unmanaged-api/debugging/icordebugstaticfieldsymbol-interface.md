---
title: Interfaccia ICorDebugStaticFieldSymbol
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a25e19bf43d852670bc5f4f491fb25707395e04a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstaticfieldsymbol-interface"></a><span data-ttu-id="4dbfe-102">Interfaccia ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="4dbfe-102">ICorDebugStaticFieldSymbol Interface</span></span>
<span data-ttu-id="4dbfe-103">Rappresenta le informazioni relative al simbolo di debug per un campo statico.</span><span class="sxs-lookup"><span data-stu-id="4dbfe-103">Represents the debug symbol information for a static field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4dbfe-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="4dbfe-104">Methods</span></span>  
  
|<span data-ttu-id="4dbfe-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="4dbfe-105">Method</span></span>|<span data-ttu-id="4dbfe-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4dbfe-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4dbfe-107">Metodo GetAddress</span><span class="sxs-lookup"><span data-stu-id="4dbfe-107">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getaddress-method.md)|<span data-ttu-id="4dbfe-108">Ottiene l'indirizzo del campo statico.</span><span class="sxs-lookup"><span data-stu-id="4dbfe-108">Gets the address of the static field.</span></span>|  
|[<span data-ttu-id="4dbfe-109">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="4dbfe-109">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getname-method.md)|<span data-ttu-id="4dbfe-110">Ottiene il nome del campo statico.</span><span class="sxs-lookup"><span data-stu-id="4dbfe-110">Gets the name of the static field.</span></span>|  
|[<span data-ttu-id="4dbfe-111">Metodo GetSize</span><span class="sxs-lookup"><span data-stu-id="4dbfe-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getsize-method.md)|<span data-ttu-id="4dbfe-112">Ottiene le dimensioni in byte del campo statico</span><span class="sxs-lookup"><span data-stu-id="4dbfe-112">Gets the size in bytes of the static field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4dbfe-113">Note</span><span class="sxs-lookup"><span data-stu-id="4dbfe-113">Remarks</span></span>  
 <span data-ttu-id="4dbfe-114">L'interfaccia `ICorDebugStaticFieldSymbol` viene usata per recuperare le informazioni sul simbolo di debug per un campo statico.</span><span class="sxs-lookup"><span data-stu-id="4dbfe-114">The `ICorDebugStaticFieldSymbol` interface is used to retrieve the debug symbol information for a static field.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4dbfe-115">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="4dbfe-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="4dbfe-116">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="4dbfe-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4dbfe-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4dbfe-117">Requirements</span></span>  
 <span data-ttu-id="4dbfe-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4dbfe-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4dbfe-119">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="4dbfe-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4dbfe-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4dbfe-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4dbfe-121">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4dbfe-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dbfe-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4dbfe-122">See Also</span></span>  
 [<span data-ttu-id="4dbfe-123">Interfaccia ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="4dbfe-123">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 [<span data-ttu-id="4dbfe-124">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="4dbfe-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="4dbfe-125">Debug</span><span class="sxs-lookup"><span data-stu-id="4dbfe-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

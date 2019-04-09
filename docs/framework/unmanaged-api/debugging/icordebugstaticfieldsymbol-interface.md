---
title: Interfaccia ICorDebugStaticFieldSymbol
ms.date: 03/30/2017
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 382f3fc9377c25379809badac0bc580c3593cbde
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103896"
---
# <a name="icordebugstaticfieldsymbol-interface"></a><span data-ttu-id="b699e-102">Interfaccia ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="b699e-102">ICorDebugStaticFieldSymbol Interface</span></span>
<span data-ttu-id="b699e-103">Rappresenta le informazioni relative al simbolo di debug per un campo statico.</span><span class="sxs-lookup"><span data-stu-id="b699e-103">Represents the debug symbol information for a static field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b699e-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="b699e-104">Methods</span></span>  
  
|<span data-ttu-id="b699e-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="b699e-105">Method</span></span>|<span data-ttu-id="b699e-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b699e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b699e-107">Metodo GetAddress</span><span class="sxs-lookup"><span data-stu-id="b699e-107">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getaddress-method.md)|<span data-ttu-id="b699e-108">Ottiene l'indirizzo del campo statico.</span><span class="sxs-lookup"><span data-stu-id="b699e-108">Gets the address of the static field.</span></span>|  
|[<span data-ttu-id="b699e-109">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="b699e-109">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getname-method.md)|<span data-ttu-id="b699e-110">Ottiene il nome del campo statico.</span><span class="sxs-lookup"><span data-stu-id="b699e-110">Gets the name of the static field.</span></span>|  
|[<span data-ttu-id="b699e-111">Metodo GetSize</span><span class="sxs-lookup"><span data-stu-id="b699e-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getsize-method.md)|<span data-ttu-id="b699e-112">Ottiene le dimensioni in byte del campo statico</span><span class="sxs-lookup"><span data-stu-id="b699e-112">Gets the size in bytes of the static field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b699e-113">Note</span><span class="sxs-lookup"><span data-stu-id="b699e-113">Remarks</span></span>  
 <span data-ttu-id="b699e-114">L'interfaccia `ICorDebugStaticFieldSymbol` viene usata per recuperare le informazioni sul simbolo di debug per un campo statico.</span><span class="sxs-lookup"><span data-stu-id="b699e-114">The `ICorDebugStaticFieldSymbol` interface is used to retrieve the debug symbol information for a static field.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b699e-115">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="b699e-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="b699e-116">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="b699e-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b699e-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b699e-117">Requirements</span></span>  
 <span data-ttu-id="b699e-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b699e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b699e-119">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b699e-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b699e-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b699e-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b699e-121">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b699e-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b699e-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b699e-122">See also</span></span>

- [<span data-ttu-id="b699e-123">Interfaccia ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="b699e-123">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="b699e-124">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="b699e-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="b699e-125">Debug</span><span class="sxs-lookup"><span data-stu-id="b699e-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

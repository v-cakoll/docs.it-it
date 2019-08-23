---
title: Interfaccia ICorDebugStaticFieldSymbol
ms.date: 03/30/2017
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7f4e245e96ac9d47db10072e50a5b3c516d5dd27
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962669"
---
# <a name="icordebugstaticfieldsymbol-interface"></a><span data-ttu-id="a36df-102">Interfaccia ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="a36df-102">ICorDebugStaticFieldSymbol Interface</span></span>
<span data-ttu-id="a36df-103">Rappresenta le informazioni relative al simbolo di debug per un campo statico.</span><span class="sxs-lookup"><span data-stu-id="a36df-103">Represents the debug symbol information for a static field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a36df-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="a36df-104">Methods</span></span>  
  
|<span data-ttu-id="a36df-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="a36df-105">Method</span></span>|<span data-ttu-id="a36df-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a36df-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a36df-107">Metodo GetAddress</span><span class="sxs-lookup"><span data-stu-id="a36df-107">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getaddress-method.md)|<span data-ttu-id="a36df-108">Ottiene l'indirizzo del campo statico.</span><span class="sxs-lookup"><span data-stu-id="a36df-108">Gets the address of the static field.</span></span>|  
|[<span data-ttu-id="a36df-109">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="a36df-109">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getname-method.md)|<span data-ttu-id="a36df-110">Ottiene il nome del campo statico.</span><span class="sxs-lookup"><span data-stu-id="a36df-110">Gets the name of the static field.</span></span>|  
|[<span data-ttu-id="a36df-111">Metodo GetSize</span><span class="sxs-lookup"><span data-stu-id="a36df-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getsize-method.md)|<span data-ttu-id="a36df-112">Ottiene le dimensioni in byte del campo statico</span><span class="sxs-lookup"><span data-stu-id="a36df-112">Gets the size in bytes of the static field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a36df-113">Note</span><span class="sxs-lookup"><span data-stu-id="a36df-113">Remarks</span></span>  
 <span data-ttu-id="a36df-114">L'interfaccia `ICorDebugStaticFieldSymbol` viene usata per recuperare le informazioni sul simbolo di debug per un campo statico.</span><span class="sxs-lookup"><span data-stu-id="a36df-114">The `ICorDebugStaticFieldSymbol` interface is used to retrieve the debug symbol information for a static field.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a36df-115">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a36df-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="a36df-116">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="a36df-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a36df-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a36df-117">Requirements</span></span>  
 <span data-ttu-id="a36df-118">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a36df-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a36df-119">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="a36df-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a36df-120">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a36df-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a36df-121">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a36df-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a36df-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a36df-122">See also</span></span>

- [<span data-ttu-id="a36df-123">Interfaccia ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="a36df-123">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="a36df-124">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a36df-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="a36df-125">Debug</span><span class="sxs-lookup"><span data-stu-id="a36df-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

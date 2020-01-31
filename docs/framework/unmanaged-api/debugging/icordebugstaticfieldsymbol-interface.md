---
title: Interfaccia ICorDebugStaticFieldSymbol
ms.date: 03/30/2017
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
ms.openlocfilehash: b50b9c8435f19e1a77229f01dc85514f5f75c9f5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791809"
---
# <a name="icordebugstaticfieldsymbol-interface"></a><span data-ttu-id="5400f-102">Interfaccia ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="5400f-102">ICorDebugStaticFieldSymbol Interface</span></span>
<span data-ttu-id="5400f-103">Rappresenta le informazioni relative al simbolo di debug per un campo statico.</span><span class="sxs-lookup"><span data-stu-id="5400f-103">Represents the debug symbol information for a static field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5400f-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="5400f-104">Methods</span></span>  
  
|<span data-ttu-id="5400f-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="5400f-105">Method</span></span>|<span data-ttu-id="5400f-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5400f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5400f-107">Metodo GetAddress</span><span class="sxs-lookup"><span data-stu-id="5400f-107">GetAddress Method</span></span>](icordebugstaticfieldsymbol-getaddress-method.md)|<span data-ttu-id="5400f-108">Ottiene l'indirizzo del campo statico.</span><span class="sxs-lookup"><span data-stu-id="5400f-108">Gets the address of the static field.</span></span>|  
|[<span data-ttu-id="5400f-109">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="5400f-109">GetName Method</span></span>](icordebugstaticfieldsymbol-getname-method.md)|<span data-ttu-id="5400f-110">Ottiene il nome del campo statico.</span><span class="sxs-lookup"><span data-stu-id="5400f-110">Gets the name of the static field.</span></span>|  
|[<span data-ttu-id="5400f-111">Metodo GetSize</span><span class="sxs-lookup"><span data-stu-id="5400f-111">GetSize Method</span></span>](icordebugstaticfieldsymbol-getsize-method.md)|<span data-ttu-id="5400f-112">Ottiene le dimensioni in byte del campo statico</span><span class="sxs-lookup"><span data-stu-id="5400f-112">Gets the size in bytes of the static field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5400f-113">Note</span><span class="sxs-lookup"><span data-stu-id="5400f-113">Remarks</span></span>  
 <span data-ttu-id="5400f-114">L'interfaccia `ICorDebugStaticFieldSymbol` viene usata per recuperare le informazioni sul simbolo di debug per un campo statico.</span><span class="sxs-lookup"><span data-stu-id="5400f-114">The `ICorDebugStaticFieldSymbol` interface is used to retrieve the debug symbol information for a static field.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5400f-115">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="5400f-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="5400f-116">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="5400f-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5400f-117">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="5400f-117">Requirements</span></span>  
 <span data-ttu-id="5400f-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5400f-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5400f-119">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5400f-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5400f-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5400f-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5400f-121">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5400f-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5400f-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5400f-122">See also</span></span>

- [<span data-ttu-id="5400f-123">Interfaccia ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="5400f-123">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="5400f-124">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="5400f-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="5400f-125">Debug</span><span class="sxs-lookup"><span data-stu-id="5400f-125">Debugging</span></span>](index.md)

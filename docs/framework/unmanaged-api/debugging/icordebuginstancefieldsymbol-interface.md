---
title: Interfaccia ICorDebugInstanceFieldSymbol
ms.date: 03/30/2017
ms.assetid: a4a8f259-b83a-4425-ae8b-72b067dbc0d9
ms.openlocfilehash: 41258b0eeed5fbf8ab86546f74073f8eeaa3085c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777519"
---
# <a name="icordebuginstancefieldsymbol-interface"></a><span data-ttu-id="b7953-102">Interfaccia ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="b7953-102">ICorDebugInstanceFieldSymbol Interface</span></span>
<span data-ttu-id="b7953-103">Rappresenta le informazioni relative al simbolo di debug per un campo di istanza.</span><span class="sxs-lookup"><span data-stu-id="b7953-103">Represents the debug symbol information for an instance field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b7953-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="b7953-104">Methods</span></span>  
  
|<span data-ttu-id="b7953-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="b7953-105">Method</span></span>|<span data-ttu-id="b7953-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b7953-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b7953-107">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="b7953-107">GetName Method</span></span>](icordebuginstancefieldsymbol-getname-method.md)|<span data-ttu-id="b7953-108">Ottiene il nome del campo di istanza.</span><span class="sxs-lookup"><span data-stu-id="b7953-108">Gets the name of the instance field.</span></span>|  
|[<span data-ttu-id="b7953-109">Metodo GetOffset</span><span class="sxs-lookup"><span data-stu-id="b7953-109">GetOffset Method</span></span>](icordebuginstancefieldsymbol-getoffset-method.md)|<span data-ttu-id="b7953-110">Ottiene l'offset, in byte, di questo campo di istanza nella relativa classe padre.</span><span class="sxs-lookup"><span data-stu-id="b7953-110">Gets the offset in bytes of this instance field in its parent class.</span></span>|  
|[<span data-ttu-id="b7953-111">Metodo GetSize</span><span class="sxs-lookup"><span data-stu-id="b7953-111">GetSize Method</span></span>](icordebuginstancefieldsymbol-getsize-method.md)|<span data-ttu-id="b7953-112">Ottiene le dimensioni, in byte, del campo di istanza.</span><span class="sxs-lookup"><span data-stu-id="b7953-112">Gets the size in bytes of the instance field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7953-113">Note</span><span class="sxs-lookup"><span data-stu-id="b7953-113">Remarks</span></span>  
 <span data-ttu-id="b7953-114">L'interfaccia `ICorDebugInstanceFieldSymbol` viene usata per recuperare le informazioni sul simbolo di debug per un campo di istanza.</span><span class="sxs-lookup"><span data-stu-id="b7953-114">The `ICorDebugInstanceFieldSymbol` interface is used to retrieve the debug symbol information for an instance field.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b7953-115">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="b7953-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="b7953-116">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="b7953-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7953-117">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="b7953-117">Requirements</span></span>  
 <span data-ttu-id="b7953-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7953-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7953-119">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7953-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7953-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7953-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7953-121">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7953-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7953-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7953-122">See also</span></span>

- [<span data-ttu-id="b7953-123">Interfaccia ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="b7953-123">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="b7953-124">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="b7953-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="b7953-125">Debug</span><span class="sxs-lookup"><span data-stu-id="b7953-125">Debugging</span></span>](index.md)

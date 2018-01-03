---
title: Interfaccia ICorDebugInstanceFieldSymbol
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a4a8f259-b83a-4425-ae8b-72b067dbc0d9
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0b13df0d70a36e475e87bae3152912e58a9f8443
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuginstancefieldsymbol-interface"></a><span data-ttu-id="4ff81-102">Interfaccia ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="4ff81-102">ICorDebugInstanceFieldSymbol Interface</span></span>
<span data-ttu-id="4ff81-103">Rappresenta le informazioni relative al simbolo di debug per un campo di istanza.</span><span class="sxs-lookup"><span data-stu-id="4ff81-103">Represents the debug symbol information for an instance field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4ff81-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="4ff81-104">Methods</span></span>  
  
|<span data-ttu-id="4ff81-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="4ff81-105">Method</span></span>|<span data-ttu-id="4ff81-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4ff81-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4ff81-107">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="4ff81-107">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getname-method.md)|<span data-ttu-id="4ff81-108">Ottiene il nome del campo di istanza.</span><span class="sxs-lookup"><span data-stu-id="4ff81-108">Gets the name of the instance field.</span></span>|  
|[<span data-ttu-id="4ff81-109">Metodo GetOffset</span><span class="sxs-lookup"><span data-stu-id="4ff81-109">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getoffset-method.md)|<span data-ttu-id="4ff81-110">Ottiene l'offset, in byte, di questo campo di istanza nella relativa classe padre.</span><span class="sxs-lookup"><span data-stu-id="4ff81-110">Gets the offset in bytes of this instance field in its parent class.</span></span>|  
|[<span data-ttu-id="4ff81-111">Metodo GetSize</span><span class="sxs-lookup"><span data-stu-id="4ff81-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getsize-method.md)|<span data-ttu-id="4ff81-112">Ottiene le dimensioni, in byte, del campo di istanza.</span><span class="sxs-lookup"><span data-stu-id="4ff81-112">Gets the size in bytes of the instance field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ff81-113">Note</span><span class="sxs-lookup"><span data-stu-id="4ff81-113">Remarks</span></span>  
 <span data-ttu-id="4ff81-114">L'interfaccia `ICorDebugInstanceFieldSymbol` viene usata per recuperare le informazioni sul simbolo di debug per un campo di istanza.</span><span class="sxs-lookup"><span data-stu-id="4ff81-114">The `ICorDebugInstanceFieldSymbol` interface is used to retrieve the debug symbol information for an instance field.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ff81-115">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="4ff81-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="4ff81-116">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="4ff81-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ff81-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4ff81-117">Requirements</span></span>  
 <span data-ttu-id="4ff81-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ff81-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ff81-119">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="4ff81-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4ff81-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ff81-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ff81-121">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ff81-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ff81-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ff81-122">See Also</span></span>  
 [<span data-ttu-id="4ff81-123">Interfaccia ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="4ff81-123">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 [<span data-ttu-id="4ff81-124">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="4ff81-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="4ff81-125">Debug</span><span class="sxs-lookup"><span data-stu-id="4ff81-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

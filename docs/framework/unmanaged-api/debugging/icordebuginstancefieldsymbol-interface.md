---
title: Interfaccia ICorDebugInstanceFieldSymbol
ms.date: 03/30/2017
ms.assetid: a4a8f259-b83a-4425-ae8b-72b067dbc0d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b5c0759989e069169c7e68b71206d9a50b04ad63
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59111488"
---
# <a name="icordebuginstancefieldsymbol-interface"></a><span data-ttu-id="61c13-102">Interfaccia ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="61c13-102">ICorDebugInstanceFieldSymbol Interface</span></span>
<span data-ttu-id="61c13-103">Rappresenta le informazioni relative al simbolo di debug per un campo di istanza.</span><span class="sxs-lookup"><span data-stu-id="61c13-103">Represents the debug symbol information for an instance field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="61c13-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="61c13-104">Methods</span></span>  
  
|<span data-ttu-id="61c13-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="61c13-105">Method</span></span>|<span data-ttu-id="61c13-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="61c13-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="61c13-107">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="61c13-107">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getname-method.md)|<span data-ttu-id="61c13-108">Ottiene il nome del campo di istanza.</span><span class="sxs-lookup"><span data-stu-id="61c13-108">Gets the name of the instance field.</span></span>|  
|[<span data-ttu-id="61c13-109">Metodo GetOffset</span><span class="sxs-lookup"><span data-stu-id="61c13-109">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getoffset-method.md)|<span data-ttu-id="61c13-110">Ottiene l'offset, in byte, di questo campo di istanza nella relativa classe padre.</span><span class="sxs-lookup"><span data-stu-id="61c13-110">Gets the offset in bytes of this instance field in its parent class.</span></span>|  
|[<span data-ttu-id="61c13-111">Metodo GetSize</span><span class="sxs-lookup"><span data-stu-id="61c13-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getsize-method.md)|<span data-ttu-id="61c13-112">Ottiene le dimensioni, in byte, del campo di istanza.</span><span class="sxs-lookup"><span data-stu-id="61c13-112">Gets the size in bytes of the instance field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61c13-113">Note</span><span class="sxs-lookup"><span data-stu-id="61c13-113">Remarks</span></span>  
 <span data-ttu-id="61c13-114">L'interfaccia `ICorDebugInstanceFieldSymbol` viene usata per recuperare le informazioni sul simbolo di debug per un campo di istanza.</span><span class="sxs-lookup"><span data-stu-id="61c13-114">The `ICorDebugInstanceFieldSymbol` interface is used to retrieve the debug symbol information for an instance field.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61c13-115">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="61c13-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="61c13-116">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="61c13-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61c13-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="61c13-117">Requirements</span></span>  
 <span data-ttu-id="61c13-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61c13-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61c13-119">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="61c13-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="61c13-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61c13-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61c13-121">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61c13-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61c13-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61c13-122">See also</span></span>

- [<span data-ttu-id="61c13-123">Interfaccia ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="61c13-123">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="61c13-124">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="61c13-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="61c13-125">Debug</span><span class="sxs-lookup"><span data-stu-id="61c13-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

---
title: Interfaccia ICorDebugStaticFieldSymbol
ms.date: 03/30/2017
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cde5f60764772ece8528eb67a82836c0ae9e651b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422458"
---
# <a name="icordebugstaticfieldsymbol-interface"></a><span data-ttu-id="3a731-102">Interfaccia ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="3a731-102">ICorDebugStaticFieldSymbol Interface</span></span>
<span data-ttu-id="3a731-103">Rappresenta le informazioni relative al simbolo di debug per un campo statico.</span><span class="sxs-lookup"><span data-stu-id="3a731-103">Represents the debug symbol information for a static field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3a731-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="3a731-104">Methods</span></span>  
  
|<span data-ttu-id="3a731-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="3a731-105">Method</span></span>|<span data-ttu-id="3a731-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a731-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3a731-107">Metodo GetAddress</span><span class="sxs-lookup"><span data-stu-id="3a731-107">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getaddress-method.md)|<span data-ttu-id="3a731-108">Ottiene l'indirizzo del campo statico.</span><span class="sxs-lookup"><span data-stu-id="3a731-108">Gets the address of the static field.</span></span>|  
|[<span data-ttu-id="3a731-109">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="3a731-109">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getname-method.md)|<span data-ttu-id="3a731-110">Ottiene il nome del campo statico.</span><span class="sxs-lookup"><span data-stu-id="3a731-110">Gets the name of the static field.</span></span>|  
|[<span data-ttu-id="3a731-111">Metodo GetSize</span><span class="sxs-lookup"><span data-stu-id="3a731-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getsize-method.md)|<span data-ttu-id="3a731-112">Ottiene le dimensioni in byte del campo statico</span><span class="sxs-lookup"><span data-stu-id="3a731-112">Gets the size in bytes of the static field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a731-113">Note</span><span class="sxs-lookup"><span data-stu-id="3a731-113">Remarks</span></span>  
 <span data-ttu-id="3a731-114">L'interfaccia `ICorDebugStaticFieldSymbol` viene usata per recuperare le informazioni sul simbolo di debug per un campo statico.</span><span class="sxs-lookup"><span data-stu-id="3a731-114">The `ICorDebugStaticFieldSymbol` interface is used to retrieve the debug symbol information for a static field.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3a731-115">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="3a731-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="3a731-116">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="3a731-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a731-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3a731-117">Requirements</span></span>  
 <span data-ttu-id="3a731-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a731-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a731-119">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="3a731-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3a731-120">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="3a731-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a731-121">**Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a731-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a731-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a731-122">See Also</span></span>  
 [<span data-ttu-id="3a731-123">Interfaccia ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="3a731-123">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 [<span data-ttu-id="3a731-124">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="3a731-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="3a731-125">Debug</span><span class="sxs-lookup"><span data-stu-id="3a731-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

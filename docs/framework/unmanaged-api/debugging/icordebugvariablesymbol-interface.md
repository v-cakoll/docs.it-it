---
title: Interfaccia ICorDebugVariableSymbol
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 0e58b85e-69bd-41ff-bedb-8cdc8be6a7a2
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 89bae73e9dfb729e26f54dc7874418163870dc27
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvariablesymbol-interface"></a><span data-ttu-id="c9c93-102">Interfaccia ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="c9c93-102">ICorDebugVariableSymbol Interface</span></span>
<span data-ttu-id="c9c93-103">Recupera le informazioni relative al simbolo di debug per una variabile.</span><span class="sxs-lookup"><span data-stu-id="c9c93-103">Retrieves the debug symbol information for a variable.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c9c93-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="c9c93-104">Methods</span></span>  
  
|<span data-ttu-id="c9c93-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="c9c93-105">Method</span></span>|<span data-ttu-id="c9c93-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c9c93-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c9c93-107">GetName (metodo)</span><span class="sxs-lookup"><span data-stu-id="c9c93-107">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getname-method.md)|<span data-ttu-id="c9c93-108">Ottiene il nome di una variabile.</span><span class="sxs-lookup"><span data-stu-id="c9c93-108">Gets the name of a variable.</span></span>|  
|[<span data-ttu-id="c9c93-109">GetSize (metodo)</span><span class="sxs-lookup"><span data-stu-id="c9c93-109">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getsize-method.md)|<span data-ttu-id="c9c93-110">Ottiene le dimensioni di una variabile in byte.</span><span class="sxs-lookup"><span data-stu-id="c9c93-110">Gets the size of a variable in bytes.</span></span>|  
|[<span data-ttu-id="c9c93-111">Metodo GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="c9c93-111">GetSlotIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getslotindex-method.md)|<span data-ttu-id="c9c93-112">Ottiene l'indice dello slot gestito di una variabile locale.</span><span class="sxs-lookup"><span data-stu-id="c9c93-112">Gets the managed slot index of a local variable.</span></span>|  
|[<span data-ttu-id="c9c93-113">GetValue (metodo)</span><span class="sxs-lookup"><span data-stu-id="c9c93-113">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getvalue-method.md)|<span data-ttu-id="c9c93-114">Ottiene il valore di una variabile come matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="c9c93-114">Gets the value of a variable as a byte array.</span></span>|  
|[<span data-ttu-id="c9c93-115">SetValue (metodo)</span><span class="sxs-lookup"><span data-stu-id="c9c93-115">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-setvalue-method.md)|<span data-ttu-id="c9c93-116">Assegna il valore di una matrice di byte a una variabile.</span><span class="sxs-lookup"><span data-stu-id="c9c93-116">Assigns the value of a byte array to a variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9c93-117">Note</span><span class="sxs-lookup"><span data-stu-id="c9c93-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9c93-118">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c9c93-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="c9c93-119">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="c9c93-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9c93-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c9c93-120">Requirements</span></span>  
 <span data-ttu-id="c9c93-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9c93-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9c93-122">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="c9c93-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c9c93-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9c93-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9c93-124">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9c93-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9c93-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9c93-125">See Also</span></span>  
 [<span data-ttu-id="c9c93-126">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="c9c93-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="c9c93-127">Debug</span><span class="sxs-lookup"><span data-stu-id="c9c93-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

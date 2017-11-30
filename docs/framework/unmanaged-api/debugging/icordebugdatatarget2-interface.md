---
title: Interfaccia ICorDebugDataTarget2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 13f11388-2f91-48d8-98d6-6a4a63cb5746
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 034e7d46c1b38aecdab18ea3a7d3b149b3d59369
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatarget2-interface"></a><span data-ttu-id="fa05f-102">Interfaccia ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="fa05f-102">ICorDebugDataTarget2 Interface</span></span>
<span data-ttu-id="fa05f-103">Estende logicamente il [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)interfaccia.</span><span class="sxs-lookup"><span data-stu-id="fa05f-103">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fa05f-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="fa05f-104">Methods</span></span>  
  
|<span data-ttu-id="fa05f-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="fa05f-105">Method</span></span>|<span data-ttu-id="fa05f-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fa05f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fa05f-107">Metodo CreateVirtualUnwinder</span><span class="sxs-lookup"><span data-stu-id="fa05f-107">CreateVirtualUnwinder Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-createvirtualunwinder-method.md)|<span data-ttu-id="fa05f-108">Crea un nuovo agente di rimozione dello stack che avvia la rimozione da un contesto iniziale (non necessariamente la foglia di un thread).</span><span class="sxs-lookup"><span data-stu-id="fa05f-108">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>|  
|[<span data-ttu-id="fa05f-109">Metodo EnumerateThreadIDs</span><span class="sxs-lookup"><span data-stu-id="fa05f-109">EnumerateThreadIDs Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-enumeratethreadids-method.md)|<span data-ttu-id="fa05f-110">Restituisce un elenco di ID thread attivi.</span><span class="sxs-lookup"><span data-stu-id="fa05f-110">Returns a list of active thread IDs.</span></span>|  
|[<span data-ttu-id="fa05f-111">Metodo GetImageFromPointer</span><span class="sxs-lookup"><span data-stu-id="fa05f-111">GetImageFromPointer Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-getimagefrompointer-method.md)|<span data-ttu-id="fa05f-112">Restituisce l'indirizzo di base e le dimensioni del modulo da un indirizzo contenuto nel modulo.</span><span class="sxs-lookup"><span data-stu-id="fa05f-112">Returns the module base address and size from an address in that module.</span></span>|  
|[<span data-ttu-id="fa05f-113">Metodo GetImageLocation</span><span class="sxs-lookup"><span data-stu-id="fa05f-113">GetImageLocation Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-getimagelocation-method.md)|<span data-ttu-id="fa05f-114">Restituisce il percorso di un modulo dall'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="fa05f-114">Returns the path of a module from the module's base address.</span></span>|  
|[<span data-ttu-id="fa05f-115">Metodo GetSymbolProviderForImage</span><span class="sxs-lookup"><span data-stu-id="fa05f-115">GetSymbolProviderForImage Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-getsymbolproviderforimage-method.md)|<span data-ttu-id="fa05f-116">Restituisce il provider di simboli per un modulo dall'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="fa05f-116">Returns the symbol-provider for a module from the base address of that module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa05f-117">Note</span><span class="sxs-lookup"><span data-stu-id="fa05f-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa05f-118">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="fa05f-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="fa05f-119">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="fa05f-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa05f-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fa05f-120">Requirements</span></span>  
 <span data-ttu-id="fa05f-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa05f-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa05f-122">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="fa05f-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fa05f-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa05f-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa05f-124">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa05f-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa05f-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa05f-125">See Also</span></span>  
 [<span data-ttu-id="fa05f-126">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="fa05f-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="fa05f-127">Debug</span><span class="sxs-lookup"><span data-stu-id="fa05f-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

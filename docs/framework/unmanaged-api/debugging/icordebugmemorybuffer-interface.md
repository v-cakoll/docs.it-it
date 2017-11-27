---
title: Interfaccia ICorDebugMemoryBuffer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 80002d064c48a90236a64a3d0a56fab5877cf411
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="f9fa1-102">Interfaccia ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="f9fa1-102">ICorDebugMemoryBuffer Interface</span></span>
<span data-ttu-id="f9fa1-103">Rappresenta un buffer in memoria.</span><span class="sxs-lookup"><span data-stu-id="f9fa1-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f9fa1-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="f9fa1-104">Methods</span></span>  
  
|<span data-ttu-id="f9fa1-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="f9fa1-105">Method</span></span>|<span data-ttu-id="f9fa1-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f9fa1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f9fa1-107">GetSize (metodo)</span><span class="sxs-lookup"><span data-stu-id="f9fa1-107">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="f9fa1-108">Ottiene le dimensioni del buffer di memoria, espresse in byte.</span><span class="sxs-lookup"><span data-stu-id="f9fa1-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="f9fa1-109">Metodo GetStartAddress</span><span class="sxs-lookup"><span data-stu-id="f9fa1-109">GetStartAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="f9fa1-110">Ottiene l'indirizzo iniziale del buffer di memoria.</span><span class="sxs-lookup"><span data-stu-id="f9fa1-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9fa1-111">Note</span><span class="sxs-lookup"><span data-stu-id="f9fa1-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f9fa1-112">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f9fa1-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="f9fa1-113">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="f9fa1-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9fa1-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f9fa1-114">Requirements</span></span>  
 <span data-ttu-id="f9fa1-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9fa1-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9fa1-116">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="f9fa1-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f9fa1-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f9fa1-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f9fa1-118">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9fa1-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9fa1-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9fa1-119">See Also</span></span>  
 [<span data-ttu-id="f9fa1-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="f9fa1-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="f9fa1-121">Debug</span><span class="sxs-lookup"><span data-stu-id="f9fa1-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

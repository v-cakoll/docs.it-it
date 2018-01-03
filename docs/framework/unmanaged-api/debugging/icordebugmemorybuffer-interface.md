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
ms.workload: dotnet
ms.openlocfilehash: 98703b07f6601307b5f26aa14b2faf67f8823be5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="a754a-102">Interfaccia ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="a754a-102">ICorDebugMemoryBuffer Interface</span></span>
<span data-ttu-id="a754a-103">Rappresenta un buffer in memoria.</span><span class="sxs-lookup"><span data-stu-id="a754a-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a754a-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="a754a-104">Methods</span></span>  
  
|<span data-ttu-id="a754a-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="a754a-105">Method</span></span>|<span data-ttu-id="a754a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a754a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a754a-107">Metodo GetSize</span><span class="sxs-lookup"><span data-stu-id="a754a-107">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="a754a-108">Ottiene le dimensioni del buffer di memoria, espresse in byte.</span><span class="sxs-lookup"><span data-stu-id="a754a-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="a754a-109">Metodo GetStartAddress</span><span class="sxs-lookup"><span data-stu-id="a754a-109">GetStartAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="a754a-110">Ottiene l'indirizzo iniziale del buffer di memoria.</span><span class="sxs-lookup"><span data-stu-id="a754a-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a754a-111">Note</span><span class="sxs-lookup"><span data-stu-id="a754a-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a754a-112">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a754a-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="a754a-113">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="a754a-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a754a-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a754a-114">Requirements</span></span>  
 <span data-ttu-id="a754a-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a754a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a754a-116">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="a754a-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a754a-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a754a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a754a-118">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a754a-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a754a-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a754a-119">See Also</span></span>  
 [<span data-ttu-id="a754a-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a754a-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="a754a-121">Debug</span><span class="sxs-lookup"><span data-stu-id="a754a-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

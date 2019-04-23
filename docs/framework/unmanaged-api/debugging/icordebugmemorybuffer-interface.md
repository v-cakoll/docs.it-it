---
title: Interfaccia ICorDebugMemoryBuffer
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e12b50e964ec470b843ae35c960f20c5675fd572
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59072909"
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="e4233-102">Interfaccia ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="e4233-102">ICorDebugMemoryBuffer Interface</span></span>
<span data-ttu-id="e4233-103">Rappresenta un buffer in memoria.</span><span class="sxs-lookup"><span data-stu-id="e4233-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e4233-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="e4233-104">Methods</span></span>  
  
|<span data-ttu-id="e4233-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="e4233-105">Method</span></span>|<span data-ttu-id="e4233-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e4233-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e4233-107">Metodo GetSize</span><span class="sxs-lookup"><span data-stu-id="e4233-107">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="e4233-108">Ottiene le dimensioni del buffer di memoria, espresse in byte.</span><span class="sxs-lookup"><span data-stu-id="e4233-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="e4233-109">Metodo GetStartAddress</span><span class="sxs-lookup"><span data-stu-id="e4233-109">GetStartAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="e4233-110">Ottiene l'indirizzo iniziale del buffer di memoria.</span><span class="sxs-lookup"><span data-stu-id="e4233-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4233-111">Note</span><span class="sxs-lookup"><span data-stu-id="e4233-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4233-112">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e4233-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="e4233-113">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="e4233-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4233-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e4233-114">Requirements</span></span>  
 <span data-ttu-id="e4233-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4233-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4233-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e4233-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e4233-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4233-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4233-118">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4233-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4233-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4233-119">See also</span></span>

- [<span data-ttu-id="e4233-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e4233-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="e4233-121">Debug</span><span class="sxs-lookup"><span data-stu-id="e4233-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

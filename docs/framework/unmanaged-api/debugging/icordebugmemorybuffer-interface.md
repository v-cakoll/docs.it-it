---
title: Interfaccia ICorDebugMemoryBuffer
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
ms.openlocfilehash: 60f3b0c3230c524ca7d308d3cb80e50b0693715d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212334"
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="db213-102">Interfaccia ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="db213-102">ICorDebugMemoryBuffer Interface</span></span>
<span data-ttu-id="db213-103">Rappresenta un buffer in memoria.</span><span class="sxs-lookup"><span data-stu-id="db213-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="db213-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="db213-104">Methods</span></span>  
  
|<span data-ttu-id="db213-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="db213-105">Method</span></span>|<span data-ttu-id="db213-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db213-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="db213-107">Metodo GetSize</span><span class="sxs-lookup"><span data-stu-id="db213-107">GetSize Method</span></span>](icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="db213-108">Ottiene le dimensioni del buffer di memoria, espresse in byte.</span><span class="sxs-lookup"><span data-stu-id="db213-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="db213-109">Metodo GetStartAddress</span><span class="sxs-lookup"><span data-stu-id="db213-109">GetStartAddress Method</span></span>](icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="db213-110">Ottiene l'indirizzo iniziale del buffer di memoria.</span><span class="sxs-lookup"><span data-stu-id="db213-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db213-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="db213-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="db213-112">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="db213-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="db213-113">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="db213-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db213-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="db213-114">Requirements</span></span>  
 <span data-ttu-id="db213-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db213-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db213-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db213-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db213-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db213-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db213-118">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db213-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db213-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db213-119">See also</span></span>

- [<span data-ttu-id="db213-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="db213-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="db213-121">Debug</span><span class="sxs-lookup"><span data-stu-id="db213-121">Debugging</span></span>](index.md)

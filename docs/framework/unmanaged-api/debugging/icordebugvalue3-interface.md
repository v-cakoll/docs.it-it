---
title: Interfaccia ICorDebugValue3
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValue3
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValue3
helpviewer_keywords: ICorDebugValue3 interface [.NET Framework debugging]
ms.assetid: 7d5385d3-f4a5-47c4-8478-a3513b5e9406
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6a470113dc54876937850294f6d99fc15a2cf98e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="143b9-102">Interfaccia ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="143b9-102">ICorDebugValue3 Interface</span></span>
<span data-ttu-id="143b9-103">Estende le interfacce "ICorDebugValue" e "ICorDebugValue2" per fornire il supporto per le matrici maggiori di 2 GB.</span><span class="sxs-lookup"><span data-stu-id="143b9-103">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="143b9-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="143b9-104">Methods</span></span>  
  
|<span data-ttu-id="143b9-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="143b9-105">Method</span></span>|<span data-ttu-id="143b9-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="143b9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="143b9-107">Metodo GetSize64</span><span class="sxs-lookup"><span data-stu-id="143b9-107">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)|<span data-ttu-id="143b9-108">Ottiene le dimensioni, in byte, di questo `ICorDebugValue3` oggetto.</span><span class="sxs-lookup"><span data-stu-id="143b9-108">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="143b9-109">Note</span><span class="sxs-lookup"><span data-stu-id="143b9-109">Remarks</span></span>  
 <span data-ttu-id="143b9-110">Il [ICorDebugValue:: GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) metodo restituisce una dimensioni dell'oggetto che va da 0 a 2.147.483.647 byte.</span><span class="sxs-lookup"><span data-stu-id="143b9-110">The [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="143b9-111">Nel [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], le dimensioni delle matrici possono superare i 2 GB.</span><span class="sxs-lookup"><span data-stu-id="143b9-111">In the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="143b9-112">Il `ICorDebugValue3` interfaccia consente di determinare le dimensioni di queste matrici.</span><span class="sxs-lookup"><span data-stu-id="143b9-112">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="143b9-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="143b9-113">Requirements</span></span>  
 <span data-ttu-id="143b9-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="143b9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="143b9-115">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="143b9-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="143b9-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="143b9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="143b9-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="143b9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="143b9-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="143b9-118">See Also</span></span>  
    
    
 [<span data-ttu-id="143b9-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="143b9-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="143b9-120">Debug</span><span class="sxs-lookup"><span data-stu-id="143b9-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

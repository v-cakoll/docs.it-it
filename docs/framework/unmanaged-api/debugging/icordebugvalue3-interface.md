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
ms.openlocfilehash: 3948a4c404036235767f8de6747966709b75bc4c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="3c59d-102">Interfaccia ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="3c59d-102">ICorDebugValue3 Interface</span></span>
<span data-ttu-id="3c59d-103">Estende le interfacce "ICorDebugValue" e "ICorDebugValue2" per fornire il supporto per le matrici maggiori di 2 GB.</span><span class="sxs-lookup"><span data-stu-id="3c59d-103">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3c59d-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="3c59d-104">Methods</span></span>  
  
|<span data-ttu-id="3c59d-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="3c59d-105">Method</span></span>|<span data-ttu-id="3c59d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3c59d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3c59d-107">GetSize64 (metodo)</span><span class="sxs-lookup"><span data-stu-id="3c59d-107">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)|<span data-ttu-id="3c59d-108">Ottiene le dimensioni, in byte, di questo `ICorDebugValue3` oggetto.</span><span class="sxs-lookup"><span data-stu-id="3c59d-108">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c59d-109">Note</span><span class="sxs-lookup"><span data-stu-id="3c59d-109">Remarks</span></span>  
 <span data-ttu-id="3c59d-110">Il [ICorDebugValue:: GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) metodo restituisce una dimensioni dell'oggetto che va da 0 a 2.147.483.647 byte.</span><span class="sxs-lookup"><span data-stu-id="3c59d-110">The [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="3c59d-111">Nel [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], le dimensioni delle matrici possono superare i 2 GB.</span><span class="sxs-lookup"><span data-stu-id="3c59d-111">In the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="3c59d-112">Il `ICorDebugValue3` interfaccia consente di determinare le dimensioni di queste matrici.</span><span class="sxs-lookup"><span data-stu-id="3c59d-112">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c59d-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3c59d-113">Requirements</span></span>  
 <span data-ttu-id="3c59d-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c59d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c59d-115">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="3c59d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3c59d-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c59d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c59d-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c59d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c59d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c59d-118">See Also</span></span>  
    
    
 [<span data-ttu-id="3c59d-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="3c59d-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="3c59d-120">Debug</span><span class="sxs-lookup"><span data-stu-id="3c59d-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

---
title: Interfaccia ICorDebugHeapValue3
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHeapValue3
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHeapValue3
helpviewer_keywords: ICorDebugHeapValue3 interface [.NET Framework debugging]
ms.assetid: 9c421bb0-e647-4b2d-a986-f3d578cc7f20
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5531689a3a4ba66fddfc98cadec7dc8d51c8629a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugheapvalue3-interface"></a><span data-ttu-id="580b2-102">Interfaccia ICorDebugHeapValue3</span><span class="sxs-lookup"><span data-stu-id="580b2-102">ICorDebugHeapValue3 Interface</span></span>
<span data-ttu-id="580b2-103">Espone le proprietà del blocco di monitoraggio di oggetti.</span><span class="sxs-lookup"><span data-stu-id="580b2-103">Exposes the monitor lock properties of objects.</span></span> <span data-ttu-id="580b2-104">Questa interfaccia estende le interfacce ICorDebugHeapValue e ICorDebugHeapValue2.</span><span class="sxs-lookup"><span data-stu-id="580b2-104">This interface extends the ICorDebugHeapValue and ICorDebugHeapValue2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="580b2-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="580b2-105">Methods</span></span>  
  
|<span data-ttu-id="580b2-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="580b2-106">Method</span></span>|<span data-ttu-id="580b2-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="580b2-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="580b2-108">GetThreadOwningMonitorLock (metodo)</span><span class="sxs-lookup"><span data-stu-id="580b2-108">GetThreadOwningMonitorLock Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-getthreadowningmonitorlock-method.md)|<span data-ttu-id="580b2-109">Restituisce il thread gestito che possiede il blocco di monitoraggio per questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="580b2-109">Returns the managed thread that owns the monitor lock on this object.</span></span>|  
|[<span data-ttu-id="580b2-110">GetMonitorEventWaitList (metodo)</span><span class="sxs-lookup"><span data-stu-id="580b2-110">GetMonitorEventWaitList Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-getmonitoreventwaitlist-method.md)|<span data-ttu-id="580b2-111">Fornisce un elenco ordinato di thread che vengono messe in coda dell'evento associato a un blocco di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="580b2-111">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="580b2-112">Note</span><span class="sxs-lookup"><span data-stu-id="580b2-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="580b2-113">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="580b2-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="580b2-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="580b2-114">Requirements</span></span>  
 <span data-ttu-id="580b2-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="580b2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="580b2-116">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="580b2-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="580b2-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="580b2-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="580b2-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="580b2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="580b2-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="580b2-119">See Also</span></span>  
 [<span data-ttu-id="580b2-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="580b2-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="580b2-121">Debug</span><span class="sxs-lookup"><span data-stu-id="580b2-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

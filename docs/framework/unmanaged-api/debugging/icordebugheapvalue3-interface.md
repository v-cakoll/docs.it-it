---
title: Interfaccia ICorDebugHeapValue3
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3
helpviewer_keywords:
- ICorDebugHeapValue3 interface [.NET Framework debugging]
ms.assetid: 9c421bb0-e647-4b2d-a986-f3d578cc7f20
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60d3b22d8dc140bf16af7f59781d5ed103dafbf4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191705"
---
# <a name="icordebugheapvalue3-interface"></a><span data-ttu-id="9dbd9-102">Interfaccia ICorDebugHeapValue3</span><span class="sxs-lookup"><span data-stu-id="9dbd9-102">ICorDebugHeapValue3 Interface</span></span>
<span data-ttu-id="9dbd9-103">Espone le proprietà del blocco di monitoraggio di oggetti.</span><span class="sxs-lookup"><span data-stu-id="9dbd9-103">Exposes the monitor lock properties of objects.</span></span> <span data-ttu-id="9dbd9-104">Questa interfaccia estende le interfacce ICorDebugHeapValue e ICorDebugHeapValue2.</span><span class="sxs-lookup"><span data-stu-id="9dbd9-104">This interface extends the ICorDebugHeapValue and ICorDebugHeapValue2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9dbd9-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="9dbd9-105">Methods</span></span>  
  
|<span data-ttu-id="9dbd9-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="9dbd9-106">Method</span></span>|<span data-ttu-id="9dbd9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9dbd9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9dbd9-108">Metodo GetThreadOwningMonitorLock</span><span class="sxs-lookup"><span data-stu-id="9dbd9-108">GetThreadOwningMonitorLock Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-getthreadowningmonitorlock-method.md)|<span data-ttu-id="9dbd9-109">Restituisce il thread gestito che possiede il blocco di monitoraggio per questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="9dbd9-109">Returns the managed thread that owns the monitor lock on this object.</span></span>|  
|[<span data-ttu-id="9dbd9-110">Metodo GetMonitorEventWaitList</span><span class="sxs-lookup"><span data-stu-id="9dbd9-110">GetMonitorEventWaitList Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-getmonitoreventwaitlist-method.md)|<span data-ttu-id="9dbd9-111">Fornisce un elenco ordinato di thread che vengono messe in coda sull'evento associato a un blocco di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="9dbd9-111">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9dbd9-112">Note</span><span class="sxs-lookup"><span data-stu-id="9dbd9-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9dbd9-113">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="9dbd9-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9dbd9-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9dbd9-114">Requirements</span></span>  
 <span data-ttu-id="9dbd9-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9dbd9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9dbd9-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9dbd9-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9dbd9-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9dbd9-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="9dbd9-118">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="9dbd9-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9dbd9-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9dbd9-119">See also</span></span>

- [<span data-ttu-id="9dbd9-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="9dbd9-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="9dbd9-121">Debug</span><span class="sxs-lookup"><span data-stu-id="9dbd9-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

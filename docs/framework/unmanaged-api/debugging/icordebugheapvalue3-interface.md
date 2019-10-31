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
ms.openlocfilehash: b062faffc22e444bd4d3b4a0c67f2a08d7af3560
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131113"
---
# <a name="icordebugheapvalue3-interface"></a><span data-ttu-id="b39b7-102">Interfaccia ICorDebugHeapValue3</span><span class="sxs-lookup"><span data-stu-id="b39b7-102">ICorDebugHeapValue3 Interface</span></span>
<span data-ttu-id="b39b7-103">Espone le proprietà del blocco di monitoraggio di oggetti.</span><span class="sxs-lookup"><span data-stu-id="b39b7-103">Exposes the monitor lock properties of objects.</span></span> <span data-ttu-id="b39b7-104">Questa interfaccia estende le interfacce ICorDebugHeapValue e ICorDebugHeapValue2.</span><span class="sxs-lookup"><span data-stu-id="b39b7-104">This interface extends the ICorDebugHeapValue and ICorDebugHeapValue2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b39b7-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="b39b7-105">Methods</span></span>  
  
|<span data-ttu-id="b39b7-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="b39b7-106">Method</span></span>|<span data-ttu-id="b39b7-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b39b7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b39b7-108">Metodo GetThreadOwningMonitorLock</span><span class="sxs-lookup"><span data-stu-id="b39b7-108">GetThreadOwningMonitorLock Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-getthreadowningmonitorlock-method.md)|<span data-ttu-id="b39b7-109">Restituisce il thread gestito proprietario del blocco di monitoraggio su questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="b39b7-109">Returns the managed thread that owns the monitor lock on this object.</span></span>|  
|[<span data-ttu-id="b39b7-110">Metodo GetMonitorEventWaitList</span><span class="sxs-lookup"><span data-stu-id="b39b7-110">GetMonitorEventWaitList Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-getmonitoreventwaitlist-method.md)|<span data-ttu-id="b39b7-111">Fornisce un elenco ordinato di thread accodati per l'evento associato a un blocco di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="b39b7-111">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b39b7-112">Note</span><span class="sxs-lookup"><span data-stu-id="b39b7-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b39b7-113">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="b39b7-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b39b7-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b39b7-114">Requirements</span></span>  
 <span data-ttu-id="b39b7-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b39b7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b39b7-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b39b7-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b39b7-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b39b7-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b39b7-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b39b7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b39b7-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b39b7-119">See also</span></span>

- [<span data-ttu-id="b39b7-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="b39b7-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="b39b7-121">Debug</span><span class="sxs-lookup"><span data-stu-id="b39b7-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

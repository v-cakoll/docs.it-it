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
ms.openlocfilehash: 24747ccea37707a474d8fff7844ee07301b8194a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69914895"
---
# <a name="icordebugheapvalue3-interface"></a><span data-ttu-id="1fadd-102">Interfaccia ICorDebugHeapValue3</span><span class="sxs-lookup"><span data-stu-id="1fadd-102">ICorDebugHeapValue3 Interface</span></span>
<span data-ttu-id="1fadd-103">Espone le proprietà del blocco di monitoraggio di oggetti.</span><span class="sxs-lookup"><span data-stu-id="1fadd-103">Exposes the monitor lock properties of objects.</span></span> <span data-ttu-id="1fadd-104">Questa interfaccia estende le interfacce ICorDebugHeapValue e ICorDebugHeapValue2.</span><span class="sxs-lookup"><span data-stu-id="1fadd-104">This interface extends the ICorDebugHeapValue and ICorDebugHeapValue2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1fadd-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="1fadd-105">Methods</span></span>  
  
|<span data-ttu-id="1fadd-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="1fadd-106">Method</span></span>|<span data-ttu-id="1fadd-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1fadd-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1fadd-108">Metodo GetThreadOwningMonitorLock</span><span class="sxs-lookup"><span data-stu-id="1fadd-108">GetThreadOwningMonitorLock Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-getthreadowningmonitorlock-method.md)|<span data-ttu-id="1fadd-109">Restituisce il thread gestito proprietario del blocco di monitoraggio su questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="1fadd-109">Returns the managed thread that owns the monitor lock on this object.</span></span>|  
|[<span data-ttu-id="1fadd-110">Metodo GetMonitorEventWaitList</span><span class="sxs-lookup"><span data-stu-id="1fadd-110">GetMonitorEventWaitList Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-getmonitoreventwaitlist-method.md)|<span data-ttu-id="1fadd-111">Fornisce un elenco ordinato di thread accodati per l'evento associato a un blocco di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="1fadd-111">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1fadd-112">Note</span><span class="sxs-lookup"><span data-stu-id="1fadd-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1fadd-113">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="1fadd-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fadd-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1fadd-114">Requirements</span></span>  
 <span data-ttu-id="1fadd-115">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1fadd-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fadd-116">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="1fadd-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1fadd-117">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1fadd-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1fadd-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fadd-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fadd-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1fadd-119">See also</span></span>

- [<span data-ttu-id="1fadd-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="1fadd-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="1fadd-121">Debug</span><span class="sxs-lookup"><span data-stu-id="1fadd-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

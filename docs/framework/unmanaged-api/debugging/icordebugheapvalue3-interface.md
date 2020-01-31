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
ms.openlocfilehash: ddfe8cee8fdbca910ffa4f6989b1359ae5f7b11f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794374"
---
# <a name="icordebugheapvalue3-interface"></a><span data-ttu-id="b7dfb-102">Interfaccia ICorDebugHeapValue3</span><span class="sxs-lookup"><span data-stu-id="b7dfb-102">ICorDebugHeapValue3 Interface</span></span>
<span data-ttu-id="b7dfb-103">Espone le proprietà del blocco di monitoraggio di oggetti.</span><span class="sxs-lookup"><span data-stu-id="b7dfb-103">Exposes the monitor lock properties of objects.</span></span> <span data-ttu-id="b7dfb-104">Questa interfaccia estende le interfacce ICorDebugHeapValue e ICorDebugHeapValue2.</span><span class="sxs-lookup"><span data-stu-id="b7dfb-104">This interface extends the ICorDebugHeapValue and ICorDebugHeapValue2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b7dfb-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="b7dfb-105">Methods</span></span>  
  
|<span data-ttu-id="b7dfb-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="b7dfb-106">Method</span></span>|<span data-ttu-id="b7dfb-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b7dfb-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b7dfb-108">Metodo GetThreadOwningMonitorLock</span><span class="sxs-lookup"><span data-stu-id="b7dfb-108">GetThreadOwningMonitorLock Method</span></span>](icordebugheapvalue3-getthreadowningmonitorlock-method.md)|<span data-ttu-id="b7dfb-109">Restituisce il thread gestito proprietario del blocco di monitoraggio su questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="b7dfb-109">Returns the managed thread that owns the monitor lock on this object.</span></span>|  
|[<span data-ttu-id="b7dfb-110">Metodo GetMonitorEventWaitList</span><span class="sxs-lookup"><span data-stu-id="b7dfb-110">GetMonitorEventWaitList Method</span></span>](icordebugheapvalue3-getmonitoreventwaitlist-method.md)|<span data-ttu-id="b7dfb-111">Fornisce un elenco ordinato di thread accodati per l'evento associato a un blocco di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="b7dfb-111">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7dfb-112">Note</span><span class="sxs-lookup"><span data-stu-id="b7dfb-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b7dfb-113">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="b7dfb-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7dfb-114">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="b7dfb-114">Requirements</span></span>  
 <span data-ttu-id="b7dfb-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7dfb-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7dfb-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7dfb-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7dfb-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7dfb-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7dfb-118">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7dfb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7dfb-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7dfb-119">See also</span></span>

- [<span data-ttu-id="b7dfb-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="b7dfb-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="b7dfb-121">Debug</span><span class="sxs-lookup"><span data-stu-id="b7dfb-121">Debugging</span></span>](index.md)

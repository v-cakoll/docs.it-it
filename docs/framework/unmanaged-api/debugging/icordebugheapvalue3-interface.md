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
ms.openlocfilehash: 5add6da1ace372ecf6e513902bbf98f5f79c6778
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210397"
---
# <a name="icordebugheapvalue3-interface"></a><span data-ttu-id="c3712-102">Interfaccia ICorDebugHeapValue3</span><span class="sxs-lookup"><span data-stu-id="c3712-102">ICorDebugHeapValue3 Interface</span></span>
<span data-ttu-id="c3712-103">Espone le proprietà del blocco di monitoraggio di oggetti.</span><span class="sxs-lookup"><span data-stu-id="c3712-103">Exposes the monitor lock properties of objects.</span></span> <span data-ttu-id="c3712-104">Questa interfaccia estende le interfacce ICorDebugHeapValue e ICorDebugHeapValue2.</span><span class="sxs-lookup"><span data-stu-id="c3712-104">This interface extends the ICorDebugHeapValue and ICorDebugHeapValue2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c3712-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="c3712-105">Methods</span></span>  
  
|<span data-ttu-id="c3712-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="c3712-106">Method</span></span>|<span data-ttu-id="c3712-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c3712-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c3712-108">Metodo GetThreadOwningMonitorLock</span><span class="sxs-lookup"><span data-stu-id="c3712-108">GetThreadOwningMonitorLock Method</span></span>](icordebugheapvalue3-getthreadowningmonitorlock-method.md)|<span data-ttu-id="c3712-109">Restituisce il thread gestito proprietario del blocco di monitoraggio su questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="c3712-109">Returns the managed thread that owns the monitor lock on this object.</span></span>|  
|[<span data-ttu-id="c3712-110">Metodo GetMonitorEventWaitList</span><span class="sxs-lookup"><span data-stu-id="c3712-110">GetMonitorEventWaitList Method</span></span>](icordebugheapvalue3-getmonitoreventwaitlist-method.md)|<span data-ttu-id="c3712-111">Fornisce un elenco ordinato di thread accodati per l'evento associato a un blocco di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="c3712-111">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3712-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c3712-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c3712-113">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="c3712-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3712-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c3712-114">Requirements</span></span>  
 <span data-ttu-id="c3712-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3712-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3712-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c3712-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c3712-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3712-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3712-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3712-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3712-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3712-119">See also</span></span>

- [<span data-ttu-id="c3712-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="c3712-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c3712-121">Debug</span><span class="sxs-lookup"><span data-stu-id="c3712-121">Debugging</span></span>](index.md)

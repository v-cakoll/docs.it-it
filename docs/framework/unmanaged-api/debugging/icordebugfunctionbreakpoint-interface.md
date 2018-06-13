---
title: ICorDebugFunctionBreakpoint Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugFunctionBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint
helpviewer_keywords:
- ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: 9c149303-14b1-4138-83d7-e8c3e0fcd332
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6cd4c430798333dd22c36ce30e7c9ce05bdc8f56
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414183"
---
# <a name="icordebugfunctionbreakpoint-interface1"></a><span data-ttu-id="b6eee-102">ICorDebugFunctionBreakpoint Interface1</span><span class="sxs-lookup"><span data-stu-id="b6eee-102">ICorDebugFunctionBreakpoint Interface1</span></span>
<span data-ttu-id="b6eee-103">Estende l'interfaccia ICorDebugBreakpoint per supportare i punti di interruzione all'interno di funzioni.</span><span class="sxs-lookup"><span data-stu-id="b6eee-103">Extends the ICorDebugBreakpoint interface to support breakpoints within functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b6eee-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="b6eee-104">Methods</span></span>  
  
|<span data-ttu-id="b6eee-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="b6eee-105">Method</span></span>|<span data-ttu-id="b6eee-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6eee-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b6eee-107">Metodo GetFunction</span><span class="sxs-lookup"><span data-stu-id="b6eee-107">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getfunction-method.md)|<span data-ttu-id="b6eee-108">Ottiene un puntatore a interfaccia ICorDebugFunction che fa riferimento alla funzione in cui è impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="b6eee-108">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>|  
|[<span data-ttu-id="b6eee-109">Metodo GetOffset</span><span class="sxs-lookup"><span data-stu-id="b6eee-109">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getoffset-method.md)|<span data-ttu-id="b6eee-110">Ottiene l'offset del punto di interruzione all'interno della funzione.</span><span class="sxs-lookup"><span data-stu-id="b6eee-110">Gets the offset of the breakpoint within the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6eee-111">Note</span><span class="sxs-lookup"><span data-stu-id="b6eee-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b6eee-112">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="b6eee-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6eee-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b6eee-113">Requirements</span></span>  
 <span data-ttu-id="b6eee-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6eee-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6eee-115">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="b6eee-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6eee-116">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="b6eee-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6eee-117">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6eee-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6eee-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6eee-118">See Also</span></span>  
 [<span data-ttu-id="b6eee-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="b6eee-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

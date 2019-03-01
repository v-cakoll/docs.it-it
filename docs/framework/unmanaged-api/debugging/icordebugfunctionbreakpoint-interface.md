---
title: Interfaccia ICorDebugFunctionBreakpoint
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
ms.openlocfilehash: 2c3c11d3b6a6daec7b35377ef24557dd5077af21
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977721"
---
# <a name="icordebugfunctionbreakpoint-interface"></a><span data-ttu-id="ffc8d-102">Interfaccia ICorDebugFunctionBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ffc8d-102">ICorDebugFunctionBreakpoint Interface</span></span>

<span data-ttu-id="ffc8d-103">Estende l'interfaccia ICorDebugBreakpoint per supportare i punti di interruzione all'interno delle funzioni.</span><span class="sxs-lookup"><span data-stu-id="ffc8d-103">Extends the ICorDebugBreakpoint interface to support breakpoints within functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ffc8d-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="ffc8d-104">Methods</span></span>  
  
|<span data-ttu-id="ffc8d-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="ffc8d-105">Method</span></span>|<span data-ttu-id="ffc8d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ffc8d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ffc8d-107">Metodo GetFunction</span><span class="sxs-lookup"><span data-stu-id="ffc8d-107">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getfunction-method.md)|<span data-ttu-id="ffc8d-108">Ottiene un puntatore a interfaccia ICorDebugFunction che fa riferimento alla funzione in cui viene impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="ffc8d-108">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>|  
|[<span data-ttu-id="ffc8d-109">Metodo GetOffset</span><span class="sxs-lookup"><span data-stu-id="ffc8d-109">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getoffset-method.md)|<span data-ttu-id="ffc8d-110">Ottiene l'offset del punto di interruzione all'interno della funzione.</span><span class="sxs-lookup"><span data-stu-id="ffc8d-110">Gets the offset of the breakpoint within the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ffc8d-111">Note</span><span class="sxs-lookup"><span data-stu-id="ffc8d-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ffc8d-112">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="ffc8d-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffc8d-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ffc8d-113">Requirements</span></span>  
 <span data-ttu-id="ffc8d-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ffc8d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffc8d-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ffc8d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ffc8d-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ffc8d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ffc8d-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffc8d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffc8d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ffc8d-118">See also</span></span>
- [<span data-ttu-id="ffc8d-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="ffc8d-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

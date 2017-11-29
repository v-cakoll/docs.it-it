---
title: ICorDebugFunctionBreakpoint Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunctionBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunctionBreakpoint
helpviewer_keywords: ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: 9c149303-14b1-4138-83d7-e8c3e0fcd332
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 910317bea8af3a80ee66544651de2372808734bb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunctionbreakpoint-interface1"></a><span data-ttu-id="dcf98-102">ICorDebugFunctionBreakpoint Interface1</span><span class="sxs-lookup"><span data-stu-id="dcf98-102">ICorDebugFunctionBreakpoint Interface1</span></span>
<span data-ttu-id="dcf98-103">Estende l'interfaccia ICorDebugBreakpoint per supportare i punti di interruzione all'interno di funzioni.</span><span class="sxs-lookup"><span data-stu-id="dcf98-103">Extends the ICorDebugBreakpoint interface to support breakpoints within functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dcf98-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="dcf98-104">Methods</span></span>  
  
|<span data-ttu-id="dcf98-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="dcf98-105">Method</span></span>|<span data-ttu-id="dcf98-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dcf98-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dcf98-107">GetFunction (metodo)</span><span class="sxs-lookup"><span data-stu-id="dcf98-107">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getfunction-method.md)|<span data-ttu-id="dcf98-108">Ottiene un puntatore a interfaccia ICorDebugFunction che fa riferimento alla funzione in cui è impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="dcf98-108">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>|  
|[<span data-ttu-id="dcf98-109">GetOffset (metodo)</span><span class="sxs-lookup"><span data-stu-id="dcf98-109">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getoffset-method.md)|<span data-ttu-id="dcf98-110">Ottiene l'offset del punto di interruzione all'interno della funzione.</span><span class="sxs-lookup"><span data-stu-id="dcf98-110">Gets the offset of the breakpoint within the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dcf98-111">Note</span><span class="sxs-lookup"><span data-stu-id="dcf98-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dcf98-112">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="dcf98-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcf98-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dcf98-113">Requirements</span></span>  
 <span data-ttu-id="dcf98-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dcf98-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcf98-115">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="dcf98-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dcf98-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dcf98-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dcf98-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcf98-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcf98-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dcf98-118">See Also</span></span>  
 [<span data-ttu-id="dcf98-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="dcf98-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

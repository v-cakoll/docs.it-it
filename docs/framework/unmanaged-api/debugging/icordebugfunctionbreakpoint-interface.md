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
ms.workload: dotnet
ms.openlocfilehash: 019a94243773fcb1751f419d8e38a6759fa1d3bd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunctionbreakpoint-interface1"></a><span data-ttu-id="63334-102">ICorDebugFunctionBreakpoint Interface1</span><span class="sxs-lookup"><span data-stu-id="63334-102">ICorDebugFunctionBreakpoint Interface1</span></span>
<span data-ttu-id="63334-103">Estende l'interfaccia ICorDebugBreakpoint per supportare i punti di interruzione all'interno di funzioni.</span><span class="sxs-lookup"><span data-stu-id="63334-103">Extends the ICorDebugBreakpoint interface to support breakpoints within functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="63334-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="63334-104">Methods</span></span>  
  
|<span data-ttu-id="63334-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="63334-105">Method</span></span>|<span data-ttu-id="63334-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="63334-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="63334-107">Metodo GetFunction</span><span class="sxs-lookup"><span data-stu-id="63334-107">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getfunction-method.md)|<span data-ttu-id="63334-108">Ottiene un puntatore a interfaccia ICorDebugFunction che fa riferimento alla funzione in cui è impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="63334-108">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>|  
|[<span data-ttu-id="63334-109">Metodo GetOffset</span><span class="sxs-lookup"><span data-stu-id="63334-109">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getoffset-method.md)|<span data-ttu-id="63334-110">Ottiene l'offset del punto di interruzione all'interno della funzione.</span><span class="sxs-lookup"><span data-stu-id="63334-110">Gets the offset of the breakpoint within the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63334-111">Note</span><span class="sxs-lookup"><span data-stu-id="63334-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63334-112">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="63334-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63334-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="63334-113">Requirements</span></span>  
 <span data-ttu-id="63334-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63334-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63334-115">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="63334-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63334-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63334-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63334-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63334-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63334-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63334-118">See Also</span></span>  
 [<span data-ttu-id="63334-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="63334-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

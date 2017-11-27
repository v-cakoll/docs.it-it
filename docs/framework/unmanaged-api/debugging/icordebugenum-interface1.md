---
title: ICorDebugEnum Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEnum
helpviewer_keywords: ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 80be7efe-2c32-4b9f-8c52-40c6f6268219
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7f6596918819294f0ab68735cec12f9eab8bf83e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugenum-interface1"></a><span data-ttu-id="922e3-102">ICorDebugEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="922e3-102">ICorDebugEnum Interface1</span></span>
<span data-ttu-id="922e3-103">Funge da interfaccia di base astratta per gli enumeratori utilizzati da un'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="922e3-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="922e3-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="922e3-104">Methods</span></span>  
  
|<span data-ttu-id="922e3-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="922e3-105">Method</span></span>|<span data-ttu-id="922e3-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="922e3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="922e3-107">Clone (metodo)</span><span class="sxs-lookup"><span data-stu-id="922e3-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-clone-method.md)|<span data-ttu-id="922e3-108">Crea una copia di questo `ICorDebugEnum` oggetto.</span><span class="sxs-lookup"><span data-stu-id="922e3-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="922e3-109">GetCount (metodo)</span><span class="sxs-lookup"><span data-stu-id="922e3-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-getcount-method.md)|<span data-ttu-id="922e3-110">Ottiene il numero di elementi nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="922e3-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="922e3-111">Reset (metodo)</span><span class="sxs-lookup"><span data-stu-id="922e3-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-reset-method.md)|<span data-ttu-id="922e3-112">Sposta il cursore all'inizio dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="922e3-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="922e3-113">Metodo Skip</span><span class="sxs-lookup"><span data-stu-id="922e3-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-skip-method.md)|<span data-ttu-id="922e3-114">Sposta in avanti il cursore nell'enumerazione per il numero specificato di elementi.</span><span class="sxs-lookup"><span data-stu-id="922e3-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="922e3-115">Note</span><span class="sxs-lookup"><span data-stu-id="922e3-115">Remarks</span></span>  
 <span data-ttu-id="922e3-116">Gli enumeratori seguenti derivano da `ICorDebugEnum`:</span><span class="sxs-lookup"><span data-stu-id="922e3-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
-   <span data-ttu-id="922e3-117">"ICorDebugAppDomainEnum"</span><span class="sxs-lookup"><span data-stu-id="922e3-117">"ICorDebugAppDomainEnum"</span></span>  
  
-   <span data-ttu-id="922e3-118">"ICorDebugAssemblyEnum"</span><span class="sxs-lookup"><span data-stu-id="922e3-118">"ICorDebugAssemblyEnum"</span></span>  
  
-   [<span data-ttu-id="922e3-119">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="922e3-119">ICorDebugBlockingObjectEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
  
-   <span data-ttu-id="922e3-120">"ICorDebugBreakpointEnum"</span><span class="sxs-lookup"><span data-stu-id="922e3-120">"ICorDebugBreakpointEnum"</span></span>  
  
-   <span data-ttu-id="922e3-121">"ICorDebugChainEnum"</span><span class="sxs-lookup"><span data-stu-id="922e3-121">"ICorDebugChainEnum"</span></span>  
  
-   <span data-ttu-id="922e3-122">"ICorDebugCodeEnum"</span><span class="sxs-lookup"><span data-stu-id="922e3-122">"ICorDebugCodeEnum"</span></span>  
  
-   <span data-ttu-id="922e3-123">"ICorDebugErrorInfoEnum"</span><span class="sxs-lookup"><span data-stu-id="922e3-123">"ICorDebugErrorInfoEnum"</span></span>  
  
-   [<span data-ttu-id="922e3-124">ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="922e3-124">ICorDebugExceptionObjectCallStackEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
  
-   <span data-ttu-id="922e3-125">"ICorDebugFrameEnum"</span><span class="sxs-lookup"><span data-stu-id="922e3-125">"ICorDebugFrameEnum"</span></span>  
  
-   [<span data-ttu-id="922e3-126">ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="922e3-126">ICorDebugGCReferenceEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
  
-   [<span data-ttu-id="922e3-127">ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="922e3-127">ICorDebugGuidToTypeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
  
-   [<span data-ttu-id="922e3-128">ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="922e3-128">ICorDebugHeapEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
  
-   [<span data-ttu-id="922e3-129">ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="922e3-129">ICorDebugHeapSegmentEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
  
-   <span data-ttu-id="922e3-130">"ICorDebugModuleEnum"</span><span class="sxs-lookup"><span data-stu-id="922e3-130">"ICorDebugModuleEnum"</span></span>  
  
-   <span data-ttu-id="922e3-131">"ICorDebugObjectEnum"</span><span class="sxs-lookup"><span data-stu-id="922e3-131">"ICorDebugObjectEnum"</span></span>  
  
-   <span data-ttu-id="922e3-132">"ICorDebugProcessEnum"</span><span class="sxs-lookup"><span data-stu-id="922e3-132">"ICorDebugProcessEnum"</span></span>  
  
-   <span data-ttu-id="922e3-133">"ICorDebugStepperEnum"</span><span class="sxs-lookup"><span data-stu-id="922e3-133">"ICorDebugStepperEnum"</span></span>  
  
-   <span data-ttu-id="922e3-134">"ICorDebugThreadEnum"</span><span class="sxs-lookup"><span data-stu-id="922e3-134">"ICorDebugThreadEnum"</span></span>  
  
-   <span data-ttu-id="922e3-135">"ICorDebugTypeEnum"</span><span class="sxs-lookup"><span data-stu-id="922e3-135">"ICorDebugTypeEnum"</span></span>  
  
-   <span data-ttu-id="922e3-136">"ICorDebugValueEnum"</span><span class="sxs-lookup"><span data-stu-id="922e3-136">"ICorDebugValueEnum"</span></span>  
  
-   [<span data-ttu-id="922e3-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="922e3-137">ICorDebugVariableHomeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
>  <span data-ttu-id="922e3-138">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="922e3-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="922e3-139">Requisiti</span><span class="sxs-lookup"><span data-stu-id="922e3-139">Requirements</span></span>  
 <span data-ttu-id="922e3-140">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="922e3-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="922e3-141">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="922e3-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="922e3-142">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="922e3-142">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="922e3-143">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="922e3-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="922e3-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="922e3-144">See Also</span></span>  
 [<span data-ttu-id="922e3-145">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="922e3-145">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

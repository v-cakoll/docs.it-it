---
title: Interfaccia ICorDebugEnum
ms.date: 03/30/2017
api_name:
- ICorDebugEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum
helpviewer_keywords:
- ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 80be7efe-2c32-4b9f-8c52-40c6f6268219
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9afaeebfdb98a404ea53b0b5ec147f8c8104e14d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148811"
---
# <a name="icordebugenum-interface"></a><span data-ttu-id="c5de8-102">Interfaccia ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="c5de8-102">ICorDebugEnum Interface</span></span>

<span data-ttu-id="c5de8-103">Funge da interfaccia di base astratta per gli enumeratori utilizzati da un'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="c5de8-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c5de8-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="c5de8-104">Methods</span></span>  
  
|<span data-ttu-id="c5de8-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="c5de8-105">Method</span></span>|<span data-ttu-id="c5de8-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c5de8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c5de8-107">Metodo Clone</span><span class="sxs-lookup"><span data-stu-id="c5de8-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-clone-method.md)|<span data-ttu-id="c5de8-108">Crea una copia di questo `ICorDebugEnum` oggetto.</span><span class="sxs-lookup"><span data-stu-id="c5de8-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="c5de8-109">Metodo GetCount</span><span class="sxs-lookup"><span data-stu-id="c5de8-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-getcount-method.md)|<span data-ttu-id="c5de8-110">Ottiene il numero di elementi nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="c5de8-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="c5de8-111">Metodo Reset</span><span class="sxs-lookup"><span data-stu-id="c5de8-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-reset-method.md)|<span data-ttu-id="c5de8-112">Sposta il cursore all'inizio dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="c5de8-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="c5de8-113">Metodo Skip</span><span class="sxs-lookup"><span data-stu-id="c5de8-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-skip-method.md)|<span data-ttu-id="c5de8-114">Sposta in avanti il cursore nell'enumerazione per il numero specificato di elementi.</span><span class="sxs-lookup"><span data-stu-id="c5de8-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5de8-115">Note</span><span class="sxs-lookup"><span data-stu-id="c5de8-115">Remarks</span></span>  
 <span data-ttu-id="c5de8-116">Gli enumeratori seguenti derivano da `ICorDebugEnum`:</span><span class="sxs-lookup"><span data-stu-id="c5de8-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
-   <span data-ttu-id="c5de8-117">"ICorDebugAppDomainEnum"</span><span class="sxs-lookup"><span data-stu-id="c5de8-117">"ICorDebugAppDomainEnum"</span></span>  
  
-   <span data-ttu-id="c5de8-118">"ICorDebugAssemblyEnum"</span><span class="sxs-lookup"><span data-stu-id="c5de8-118">"ICorDebugAssemblyEnum"</span></span>  
  
-   [<span data-ttu-id="c5de8-119">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="c5de8-119">ICorDebugBlockingObjectEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
  
-   <span data-ttu-id="c5de8-120">"ICorDebugBreakpointEnum"</span><span class="sxs-lookup"><span data-stu-id="c5de8-120">"ICorDebugBreakpointEnum"</span></span>  
  
-   <span data-ttu-id="c5de8-121">"ICorDebugChainEnum"</span><span class="sxs-lookup"><span data-stu-id="c5de8-121">"ICorDebugChainEnum"</span></span>  
  
-   <span data-ttu-id="c5de8-122">"ICorDebugCodeEnum"</span><span class="sxs-lookup"><span data-stu-id="c5de8-122">"ICorDebugCodeEnum"</span></span>  
  
-   <span data-ttu-id="c5de8-123">"ICorDebugErrorInfoEnum"</span><span class="sxs-lookup"><span data-stu-id="c5de8-123">"ICorDebugErrorInfoEnum"</span></span>  
  
-   [<span data-ttu-id="c5de8-124">ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="c5de8-124">ICorDebugExceptionObjectCallStackEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
  
-   <span data-ttu-id="c5de8-125">"ICorDebugFrameEnum"</span><span class="sxs-lookup"><span data-stu-id="c5de8-125">"ICorDebugFrameEnum"</span></span>  
  
-   [<span data-ttu-id="c5de8-126">ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="c5de8-126">ICorDebugGCReferenceEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
  
-   [<span data-ttu-id="c5de8-127">ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="c5de8-127">ICorDebugGuidToTypeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
  
-   [<span data-ttu-id="c5de8-128">ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="c5de8-128">ICorDebugHeapEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
  
-   [<span data-ttu-id="c5de8-129">ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="c5de8-129">ICorDebugHeapSegmentEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
  
-   <span data-ttu-id="c5de8-130">"ICorDebugModuleEnum"</span><span class="sxs-lookup"><span data-stu-id="c5de8-130">"ICorDebugModuleEnum"</span></span>  
  
-   <span data-ttu-id="c5de8-131">"ICorDebugObjectEnum"</span><span class="sxs-lookup"><span data-stu-id="c5de8-131">"ICorDebugObjectEnum"</span></span>  
  
-   <span data-ttu-id="c5de8-132">"ICorDebugProcessEnum"</span><span class="sxs-lookup"><span data-stu-id="c5de8-132">"ICorDebugProcessEnum"</span></span>  
  
-   <span data-ttu-id="c5de8-133">"ICorDebugStepperEnum"</span><span class="sxs-lookup"><span data-stu-id="c5de8-133">"ICorDebugStepperEnum"</span></span>  
  
-   <span data-ttu-id="c5de8-134">"ICorDebugThreadEnum"</span><span class="sxs-lookup"><span data-stu-id="c5de8-134">"ICorDebugThreadEnum"</span></span>  
  
-   <span data-ttu-id="c5de8-135">"ICorDebugTypeEnum"</span><span class="sxs-lookup"><span data-stu-id="c5de8-135">"ICorDebugTypeEnum"</span></span>  
  
-   <span data-ttu-id="c5de8-136">"ICorDebugValueEnum"</span><span class="sxs-lookup"><span data-stu-id="c5de8-136">"ICorDebugValueEnum"</span></span>  
  
-   [<span data-ttu-id="c5de8-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="c5de8-137">ICorDebugVariableHomeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
>  <span data-ttu-id="c5de8-138">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="c5de8-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5de8-139">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c5de8-139">Requirements</span></span>  
 <span data-ttu-id="c5de8-140">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5de8-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5de8-141">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c5de8-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c5de8-142">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5de8-142">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c5de8-143">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c5de8-143">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c5de8-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5de8-144">See also</span></span>

- [<span data-ttu-id="c5de8-145">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="c5de8-145">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

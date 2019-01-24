---
title: Interfaccia1 ICorDebugEnum
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
ms.openlocfilehash: 97080f7d850e67d635f9a65ee85ad3ddddbb244d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54732752"
---
# <a name="icordebugenum-interface1"></a><span data-ttu-id="60f13-102">Interfaccia1 ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="60f13-102">ICorDebugEnum Interface1</span></span>
<span data-ttu-id="60f13-103">Funge da interfaccia di base astratta per gli enumeratori utilizzati da un'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="60f13-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="60f13-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="60f13-104">Methods</span></span>  
  
|<span data-ttu-id="60f13-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="60f13-105">Method</span></span>|<span data-ttu-id="60f13-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="60f13-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="60f13-107">Metodo Clone</span><span class="sxs-lookup"><span data-stu-id="60f13-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-clone-method.md)|<span data-ttu-id="60f13-108">Crea una copia di questo `ICorDebugEnum` oggetto.</span><span class="sxs-lookup"><span data-stu-id="60f13-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="60f13-109">Metodo GetCount</span><span class="sxs-lookup"><span data-stu-id="60f13-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-getcount-method.md)|<span data-ttu-id="60f13-110">Ottiene il numero di elementi nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="60f13-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="60f13-111">Metodo Reset</span><span class="sxs-lookup"><span data-stu-id="60f13-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-reset-method.md)|<span data-ttu-id="60f13-112">Sposta il cursore all'inizio dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="60f13-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="60f13-113">Metodo Skip</span><span class="sxs-lookup"><span data-stu-id="60f13-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-skip-method.md)|<span data-ttu-id="60f13-114">Sposta in avanti il cursore nell'enumerazione per il numero specificato di elementi.</span><span class="sxs-lookup"><span data-stu-id="60f13-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60f13-115">Note</span><span class="sxs-lookup"><span data-stu-id="60f13-115">Remarks</span></span>  
 <span data-ttu-id="60f13-116">Gli enumeratori seguenti derivano da `ICorDebugEnum`:</span><span class="sxs-lookup"><span data-stu-id="60f13-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
-   <span data-ttu-id="60f13-117">"ICorDebugAppDomainEnum"</span><span class="sxs-lookup"><span data-stu-id="60f13-117">"ICorDebugAppDomainEnum"</span></span>  
  
-   <span data-ttu-id="60f13-118">"ICorDebugAssemblyEnum"</span><span class="sxs-lookup"><span data-stu-id="60f13-118">"ICorDebugAssemblyEnum"</span></span>  
  
-   [<span data-ttu-id="60f13-119">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="60f13-119">ICorDebugBlockingObjectEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
  
-   <span data-ttu-id="60f13-120">"ICorDebugBreakpointEnum"</span><span class="sxs-lookup"><span data-stu-id="60f13-120">"ICorDebugBreakpointEnum"</span></span>  
  
-   <span data-ttu-id="60f13-121">"ICorDebugChainEnum"</span><span class="sxs-lookup"><span data-stu-id="60f13-121">"ICorDebugChainEnum"</span></span>  
  
-   <span data-ttu-id="60f13-122">"ICorDebugCodeEnum"</span><span class="sxs-lookup"><span data-stu-id="60f13-122">"ICorDebugCodeEnum"</span></span>  
  
-   <span data-ttu-id="60f13-123">"ICorDebugErrorInfoEnum"</span><span class="sxs-lookup"><span data-stu-id="60f13-123">"ICorDebugErrorInfoEnum"</span></span>  
  
-   [<span data-ttu-id="60f13-124">ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="60f13-124">ICorDebugExceptionObjectCallStackEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
  
-   <span data-ttu-id="60f13-125">"ICorDebugFrameEnum"</span><span class="sxs-lookup"><span data-stu-id="60f13-125">"ICorDebugFrameEnum"</span></span>  
  
-   [<span data-ttu-id="60f13-126">ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="60f13-126">ICorDebugGCReferenceEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
  
-   [<span data-ttu-id="60f13-127">ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="60f13-127">ICorDebugGuidToTypeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
  
-   [<span data-ttu-id="60f13-128">ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="60f13-128">ICorDebugHeapEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
  
-   [<span data-ttu-id="60f13-129">ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="60f13-129">ICorDebugHeapSegmentEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
  
-   <span data-ttu-id="60f13-130">"ICorDebugModuleEnum"</span><span class="sxs-lookup"><span data-stu-id="60f13-130">"ICorDebugModuleEnum"</span></span>  
  
-   <span data-ttu-id="60f13-131">"ICorDebugObjectEnum"</span><span class="sxs-lookup"><span data-stu-id="60f13-131">"ICorDebugObjectEnum"</span></span>  
  
-   <span data-ttu-id="60f13-132">"ICorDebugProcessEnum"</span><span class="sxs-lookup"><span data-stu-id="60f13-132">"ICorDebugProcessEnum"</span></span>  
  
-   <span data-ttu-id="60f13-133">"ICorDebugStepperEnum"</span><span class="sxs-lookup"><span data-stu-id="60f13-133">"ICorDebugStepperEnum"</span></span>  
  
-   <span data-ttu-id="60f13-134">"ICorDebugThreadEnum"</span><span class="sxs-lookup"><span data-stu-id="60f13-134">"ICorDebugThreadEnum"</span></span>  
  
-   <span data-ttu-id="60f13-135">"ICorDebugTypeEnum"</span><span class="sxs-lookup"><span data-stu-id="60f13-135">"ICorDebugTypeEnum"</span></span>  
  
-   <span data-ttu-id="60f13-136">"ICorDebugValueEnum"</span><span class="sxs-lookup"><span data-stu-id="60f13-136">"ICorDebugValueEnum"</span></span>  
  
-   [<span data-ttu-id="60f13-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="60f13-137">ICorDebugVariableHomeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
>  <span data-ttu-id="60f13-138">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="60f13-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60f13-139">Requisiti</span><span class="sxs-lookup"><span data-stu-id="60f13-139">Requirements</span></span>  
 <span data-ttu-id="60f13-140">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60f13-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60f13-141">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="60f13-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="60f13-142">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60f13-142">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60f13-143">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60f13-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60f13-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60f13-144">See also</span></span>
- [<span data-ttu-id="60f13-145">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="60f13-145">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

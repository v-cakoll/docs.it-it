---
title: ICorDebugEnum Interface1
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
ms.openlocfilehash: a4659bbc9c2e3c71a6cf85e51a06bee4f789356b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422305"
---
# <a name="icordebugenum-interface1"></a><span data-ttu-id="41150-102">ICorDebugEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="41150-102">ICorDebugEnum Interface1</span></span>
<span data-ttu-id="41150-103">Funge da interfaccia di base astratta per gli enumeratori utilizzati da un'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="41150-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="41150-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="41150-104">Methods</span></span>  
  
|<span data-ttu-id="41150-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="41150-105">Method</span></span>|<span data-ttu-id="41150-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41150-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="41150-107">Metodo Clone</span><span class="sxs-lookup"><span data-stu-id="41150-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-clone-method.md)|<span data-ttu-id="41150-108">Crea una copia di questo `ICorDebugEnum` oggetto.</span><span class="sxs-lookup"><span data-stu-id="41150-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="41150-109">Metodo GetCount</span><span class="sxs-lookup"><span data-stu-id="41150-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-getcount-method.md)|<span data-ttu-id="41150-110">Ottiene il numero di elementi nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="41150-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="41150-111">Metodo Reset</span><span class="sxs-lookup"><span data-stu-id="41150-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-reset-method.md)|<span data-ttu-id="41150-112">Sposta il cursore all'inizio dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="41150-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="41150-113">Metodo Skip</span><span class="sxs-lookup"><span data-stu-id="41150-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-skip-method.md)|<span data-ttu-id="41150-114">Sposta in avanti il cursore nell'enumerazione per il numero specificato di elementi.</span><span class="sxs-lookup"><span data-stu-id="41150-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41150-115">Note</span><span class="sxs-lookup"><span data-stu-id="41150-115">Remarks</span></span>  
 <span data-ttu-id="41150-116">Gli enumeratori seguenti derivano da `ICorDebugEnum`:</span><span class="sxs-lookup"><span data-stu-id="41150-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
-   <span data-ttu-id="41150-117">"ICorDebugAppDomainEnum"</span><span class="sxs-lookup"><span data-stu-id="41150-117">"ICorDebugAppDomainEnum"</span></span>  
  
-   <span data-ttu-id="41150-118">"ICorDebugAssemblyEnum"</span><span class="sxs-lookup"><span data-stu-id="41150-118">"ICorDebugAssemblyEnum"</span></span>  
  
-   [<span data-ttu-id="41150-119">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="41150-119">ICorDebugBlockingObjectEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
  
-   <span data-ttu-id="41150-120">"ICorDebugBreakpointEnum"</span><span class="sxs-lookup"><span data-stu-id="41150-120">"ICorDebugBreakpointEnum"</span></span>  
  
-   <span data-ttu-id="41150-121">"ICorDebugChainEnum"</span><span class="sxs-lookup"><span data-stu-id="41150-121">"ICorDebugChainEnum"</span></span>  
  
-   <span data-ttu-id="41150-122">"ICorDebugCodeEnum"</span><span class="sxs-lookup"><span data-stu-id="41150-122">"ICorDebugCodeEnum"</span></span>  
  
-   <span data-ttu-id="41150-123">"ICorDebugErrorInfoEnum"</span><span class="sxs-lookup"><span data-stu-id="41150-123">"ICorDebugErrorInfoEnum"</span></span>  
  
-   [<span data-ttu-id="41150-124">ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="41150-124">ICorDebugExceptionObjectCallStackEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
  
-   <span data-ttu-id="41150-125">"ICorDebugFrameEnum"</span><span class="sxs-lookup"><span data-stu-id="41150-125">"ICorDebugFrameEnum"</span></span>  
  
-   [<span data-ttu-id="41150-126">ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="41150-126">ICorDebugGCReferenceEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
  
-   [<span data-ttu-id="41150-127">ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="41150-127">ICorDebugGuidToTypeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
  
-   [<span data-ttu-id="41150-128">ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="41150-128">ICorDebugHeapEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
  
-   [<span data-ttu-id="41150-129">ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="41150-129">ICorDebugHeapSegmentEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
  
-   <span data-ttu-id="41150-130">"ICorDebugModuleEnum"</span><span class="sxs-lookup"><span data-stu-id="41150-130">"ICorDebugModuleEnum"</span></span>  
  
-   <span data-ttu-id="41150-131">"ICorDebugObjectEnum"</span><span class="sxs-lookup"><span data-stu-id="41150-131">"ICorDebugObjectEnum"</span></span>  
  
-   <span data-ttu-id="41150-132">"ICorDebugProcessEnum"</span><span class="sxs-lookup"><span data-stu-id="41150-132">"ICorDebugProcessEnum"</span></span>  
  
-   <span data-ttu-id="41150-133">"ICorDebugStepperEnum"</span><span class="sxs-lookup"><span data-stu-id="41150-133">"ICorDebugStepperEnum"</span></span>  
  
-   <span data-ttu-id="41150-134">"ICorDebugThreadEnum"</span><span class="sxs-lookup"><span data-stu-id="41150-134">"ICorDebugThreadEnum"</span></span>  
  
-   <span data-ttu-id="41150-135">"ICorDebugTypeEnum"</span><span class="sxs-lookup"><span data-stu-id="41150-135">"ICorDebugTypeEnum"</span></span>  
  
-   <span data-ttu-id="41150-136">"ICorDebugValueEnum"</span><span class="sxs-lookup"><span data-stu-id="41150-136">"ICorDebugValueEnum"</span></span>  
  
-   [<span data-ttu-id="41150-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="41150-137">ICorDebugVariableHomeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
>  <span data-ttu-id="41150-138">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="41150-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41150-139">Requisiti</span><span class="sxs-lookup"><span data-stu-id="41150-139">Requirements</span></span>  
 <span data-ttu-id="41150-140">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41150-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41150-141">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="41150-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41150-142">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="41150-142">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41150-143">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41150-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41150-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41150-144">See Also</span></span>  
 [<span data-ttu-id="41150-145">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="41150-145">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

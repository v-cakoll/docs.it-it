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
ms.openlocfilehash: 7575be3f5074243b251c80b8dd5bdbb12e5d50fd
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976327"
---
# <a name="icordebugenum-interface"></a><span data-ttu-id="e4c85-102">Interfaccia ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="e4c85-102">ICorDebugEnum Interface</span></span>

<span data-ttu-id="e4c85-103">Funge da interfaccia di base astratta per gli enumeratori utilizzati da un'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="e4c85-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e4c85-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="e4c85-104">Methods</span></span>  
  
|<span data-ttu-id="e4c85-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="e4c85-105">Method</span></span>|<span data-ttu-id="e4c85-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e4c85-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e4c85-107">Metodo Clone</span><span class="sxs-lookup"><span data-stu-id="e4c85-107">Clone Method</span></span>](icordebugenum-clone-method.md)|<span data-ttu-id="e4c85-108">Crea una copia dell'oggetto `ICorDebugEnum`.</span><span class="sxs-lookup"><span data-stu-id="e4c85-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="e4c85-109">Metodo GetCount</span><span class="sxs-lookup"><span data-stu-id="e4c85-109">GetCount Method</span></span>](icordebugenum-getcount-method.md)|<span data-ttu-id="e4c85-110">Ottiene il numero di elementi nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="e4c85-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="e4c85-111">Metodo Reset</span><span class="sxs-lookup"><span data-stu-id="e4c85-111">Reset Method</span></span>](icordebugenum-reset-method.md)|<span data-ttu-id="e4c85-112">Sposta il cursore all'inizio dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="e4c85-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="e4c85-113">Metodo Skip</span><span class="sxs-lookup"><span data-stu-id="e4c85-113">Skip Method</span></span>](icordebugenum-skip-method.md)|<span data-ttu-id="e4c85-114">Sposta il cursore verso l'interno dell'enumerazione in base al numero di elementi specificato.</span><span class="sxs-lookup"><span data-stu-id="e4c85-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4c85-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e4c85-115">Remarks</span></span>  
 <span data-ttu-id="e4c85-116">Gli enumeratori seguenti derivano `ICorDebugEnum`da:</span><span class="sxs-lookup"><span data-stu-id="e4c85-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
- <span data-ttu-id="e4c85-117">ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="e4c85-117">"ICorDebugAppDomainEnum"</span></span>  
  
- <span data-ttu-id="e4c85-118">ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="e4c85-118">"ICorDebugAssemblyEnum"</span></span>  
  
- [<span data-ttu-id="e4c85-119">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="e4c85-119">ICorDebugBlockingObjectEnum</span></span>](icordebugblockingobjectenum-interface.md)  
  
- <span data-ttu-id="e4c85-120">ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="e4c85-120">"ICorDebugBreakpointEnum"</span></span>  
  
- <span data-ttu-id="e4c85-121">ICorDebugChainEnum</span><span class="sxs-lookup"><span data-stu-id="e4c85-121">"ICorDebugChainEnum"</span></span>  
  
- <span data-ttu-id="e4c85-122">ICorDebugCodeEnum</span><span class="sxs-lookup"><span data-stu-id="e4c85-122">"ICorDebugCodeEnum"</span></span>  
  
- <span data-ttu-id="e4c85-123">ICorDebugErrorInfoEnum</span><span class="sxs-lookup"><span data-stu-id="e4c85-123">"ICorDebugErrorInfoEnum"</span></span>  
  
- [<span data-ttu-id="e4c85-124">ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="e4c85-124">ICorDebugExceptionObjectCallStackEnum</span></span>](icordebugexceptionobjectcallstackenum-interface.md)  
  
- <span data-ttu-id="e4c85-125">ICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="e4c85-125">"ICorDebugFrameEnum"</span></span>  
  
- [<span data-ttu-id="e4c85-126">ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="e4c85-126">ICorDebugGCReferenceEnum</span></span>](icordebuggcreferenceenum-interface.md)  
  
- [<span data-ttu-id="e4c85-127">ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="e4c85-127">ICorDebugGuidToTypeEnum</span></span>](icordebugguidtotypeenum-interface.md)  
  
- [<span data-ttu-id="e4c85-128">ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="e4c85-128">ICorDebugHeapEnum</span></span>](icordebugheapenum-interface.md)  
  
- [<span data-ttu-id="e4c85-129">ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="e4c85-129">ICorDebugHeapSegmentEnum</span></span>](icordebugheapsegmentenum-interface.md)  
  
- <span data-ttu-id="e4c85-130">ICorDebugModuleEnum</span><span class="sxs-lookup"><span data-stu-id="e4c85-130">"ICorDebugModuleEnum"</span></span>  
  
- <span data-ttu-id="e4c85-131">ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="e4c85-131">"ICorDebugObjectEnum"</span></span>  
  
- <span data-ttu-id="e4c85-132">ICorDebugProcessEnum</span><span class="sxs-lookup"><span data-stu-id="e4c85-132">"ICorDebugProcessEnum"</span></span>  
  
- <span data-ttu-id="e4c85-133">ICorDebugStepperEnum</span><span class="sxs-lookup"><span data-stu-id="e4c85-133">"ICorDebugStepperEnum"</span></span>  
  
- <span data-ttu-id="e4c85-134">ICorDebugThreadEnum</span><span class="sxs-lookup"><span data-stu-id="e4c85-134">"ICorDebugThreadEnum"</span></span>  
  
- <span data-ttu-id="e4c85-135">ICorDebugTypeEnum</span><span class="sxs-lookup"><span data-stu-id="e4c85-135">"ICorDebugTypeEnum"</span></span>  
  
- <span data-ttu-id="e4c85-136">ICorDebugValueEnum</span><span class="sxs-lookup"><span data-stu-id="e4c85-136">"ICorDebugValueEnum"</span></span>  
  
- [<span data-ttu-id="e4c85-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="e4c85-137">ICorDebugVariableHomeEnum</span></span>](icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
> <span data-ttu-id="e4c85-138">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="e4c85-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4c85-139">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e4c85-139">Requirements</span></span>  
 <span data-ttu-id="e4c85-140">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4c85-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4c85-141">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e4c85-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e4c85-142">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4c85-142">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4c85-143">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4c85-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4c85-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4c85-144">See also</span></span>

- [<span data-ttu-id="e4c85-145">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e4c85-145">Debugging Interfaces</span></span>](debugging-interfaces.md)

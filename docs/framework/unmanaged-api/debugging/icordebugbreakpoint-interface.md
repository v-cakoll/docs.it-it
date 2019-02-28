---
title: Interfaccia ICorDebugBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint
helpviewer_keywords:
- ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: aa5ad3d7-e1bb-42af-99bc-471224e3bcaa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a7e454c15ddfa977a6d06921a5d80a6c05dca92f
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973574"
---
# <a name="icordebugbreakpoint-interface"></a><span data-ttu-id="54bd3-102">Interfaccia ICorDebugBreakpoint</span><span class="sxs-lookup"><span data-stu-id="54bd3-102">ICorDebugBreakpoint Interface</span></span>

<span data-ttu-id="54bd3-103">Rappresenta un punto di interruzione in una funzione o un punto di controllo su un valore.</span><span class="sxs-lookup"><span data-stu-id="54bd3-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="54bd3-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="54bd3-104">Methods</span></span>  
  
|<span data-ttu-id="54bd3-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="54bd3-105">Method</span></span>|<span data-ttu-id="54bd3-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="54bd3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="54bd3-107">Metodo Activate</span><span class="sxs-lookup"><span data-stu-id="54bd3-107">Activate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|<span data-ttu-id="54bd3-108">Imposta lo stato attivo di questa `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="54bd3-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="54bd3-109">Metodo IsActive</span><span class="sxs-lookup"><span data-stu-id="54bd3-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="54bd3-110">Ottiene un valore che indica se questo `ICorDebugBreakpoint` è attiva.</span><span class="sxs-lookup"><span data-stu-id="54bd3-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54bd3-111">Note</span><span class="sxs-lookup"><span data-stu-id="54bd3-111">Remarks</span></span>  
 <span data-ttu-id="54bd3-112">I punti di interruzione non supportano direttamente le espressioni condizionali.</span><span class="sxs-lookup"><span data-stu-id="54bd3-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="54bd3-113">Se si desidera tale funzionalità, un debugger necessario implementarla nella parte superiore della `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="54bd3-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="54bd3-114">Estende l'interfaccia ICorDebugFunctionBreakpoint `ICorDebugBreakpoint` per supportare i punti di interruzione all'interno delle funzioni.</span><span class="sxs-lookup"><span data-stu-id="54bd3-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54bd3-115">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="54bd3-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54bd3-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="54bd3-116">Requirements</span></span>  
 <span data-ttu-id="54bd3-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54bd3-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54bd3-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54bd3-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54bd3-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54bd3-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54bd3-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54bd3-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54bd3-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54bd3-121">See also</span></span>
- [<span data-ttu-id="54bd3-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="54bd3-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

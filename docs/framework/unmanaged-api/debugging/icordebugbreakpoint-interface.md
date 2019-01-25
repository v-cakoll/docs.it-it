---
title: Interfaccia1 ICorDebugBreakpoint
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
ms.openlocfilehash: a222f578daed0ab81e2136e00d6f9b032acd95fc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54744934"
---
# <a name="icordebugbreakpoint-interface1"></a><span data-ttu-id="e4022-102">Interfaccia1 ICorDebugBreakpoint</span><span class="sxs-lookup"><span data-stu-id="e4022-102">ICorDebugBreakpoint Interface1</span></span>
<span data-ttu-id="e4022-103">Rappresenta un punto di interruzione in una funzione o un punto di controllo su un valore.</span><span class="sxs-lookup"><span data-stu-id="e4022-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e4022-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="e4022-104">Methods</span></span>  
  
|<span data-ttu-id="e4022-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="e4022-105">Method</span></span>|<span data-ttu-id="e4022-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e4022-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e4022-107">Metodo Activate</span><span class="sxs-lookup"><span data-stu-id="e4022-107">Activate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|<span data-ttu-id="e4022-108">Imposta lo stato attivo di questa `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="e4022-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="e4022-109">Metodo IsActive</span><span class="sxs-lookup"><span data-stu-id="e4022-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="e4022-110">Ottiene un valore che indica se questo `ICorDebugBreakpoint` è attiva.</span><span class="sxs-lookup"><span data-stu-id="e4022-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4022-111">Note</span><span class="sxs-lookup"><span data-stu-id="e4022-111">Remarks</span></span>  
 <span data-ttu-id="e4022-112">I punti di interruzione non supportano direttamente le espressioni condizionali.</span><span class="sxs-lookup"><span data-stu-id="e4022-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="e4022-113">Se si desidera tale funzionalità, un debugger necessario implementarla nella parte superiore della `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="e4022-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="e4022-114">Estende l'interfaccia ICorDebugFunctionBreakpoint `ICorDebugBreakpoint` per supportare i punti di interruzione all'interno delle funzioni.</span><span class="sxs-lookup"><span data-stu-id="e4022-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4022-115">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="e4022-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4022-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e4022-116">Requirements</span></span>  
 <span data-ttu-id="e4022-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4022-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4022-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e4022-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e4022-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4022-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4022-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4022-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4022-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4022-121">See also</span></span>
- [<span data-ttu-id="e4022-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e4022-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

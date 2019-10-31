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
ms.openlocfilehash: 29bb84341c2cb4177c43f798d25a1a6d50099aa5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122785"
---
# <a name="icordebugbreakpoint-interface"></a><span data-ttu-id="650ce-102">Interfaccia ICorDebugBreakpoint</span><span class="sxs-lookup"><span data-stu-id="650ce-102">ICorDebugBreakpoint Interface</span></span>

<span data-ttu-id="650ce-103">Rappresenta un punto di interruzione in una funzione o un punto di controllo su un valore.</span><span class="sxs-lookup"><span data-stu-id="650ce-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="650ce-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="650ce-104">Methods</span></span>  
  
|<span data-ttu-id="650ce-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="650ce-105">Method</span></span>|<span data-ttu-id="650ce-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="650ce-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="650ce-107">Metodo Activate</span><span class="sxs-lookup"><span data-stu-id="650ce-107">Activate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|<span data-ttu-id="650ce-108">Imposta lo stato attivo di questo `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="650ce-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="650ce-109">Metodo IsActive</span><span class="sxs-lookup"><span data-stu-id="650ce-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="650ce-110">Ottiene un valore che indica se questo `ICorDebugBreakpoint` è attivo.</span><span class="sxs-lookup"><span data-stu-id="650ce-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="650ce-111">Note</span><span class="sxs-lookup"><span data-stu-id="650ce-111">Remarks</span></span>  
 <span data-ttu-id="650ce-112">I punti di interruzione non supportano direttamente le espressioni condizionali.</span><span class="sxs-lookup"><span data-stu-id="650ce-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="650ce-113">Se si desidera questa funzionalità, un debugger deve implementarlo sopra `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="650ce-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="650ce-114">L'interfaccia ICorDebugFunctionBreakpoint estende `ICorDebugBreakpoint` per supportare i punti di interruzione all'interno di funzioni.</span><span class="sxs-lookup"><span data-stu-id="650ce-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="650ce-115">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="650ce-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="650ce-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="650ce-116">Requirements</span></span>  
 <span data-ttu-id="650ce-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="650ce-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="650ce-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="650ce-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="650ce-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="650ce-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="650ce-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="650ce-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="650ce-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="650ce-121">See also</span></span>

- [<span data-ttu-id="650ce-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="650ce-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

---
title: ICorDebugBreakpoint Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugBreakpoint
helpviewer_keywords: ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: aa5ad3d7-e1bb-42af-99bc-471224e3bcaa
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cd2c4245b5e3dcc4f7b989a3ca9add8d568467cb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugbreakpoint-interface1"></a><span data-ttu-id="f0b4e-102">ICorDebugBreakpoint Interface1</span><span class="sxs-lookup"><span data-stu-id="f0b4e-102">ICorDebugBreakpoint Interface1</span></span>
<span data-ttu-id="f0b4e-103">Rappresenta un punto di interruzione in una funzione o un punto di controllo su un valore.</span><span class="sxs-lookup"><span data-stu-id="f0b4e-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f0b4e-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="f0b4e-104">Methods</span></span>  
  
|<span data-ttu-id="f0b4e-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="f0b4e-105">Method</span></span>|<span data-ttu-id="f0b4e-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f0b4e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f0b4e-107">Metodo Activate</span><span class="sxs-lookup"><span data-stu-id="f0b4e-107">Activate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|<span data-ttu-id="f0b4e-108">Imposta lo stato attivo di questo `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="f0b4e-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="f0b4e-109">Metodo IsActive</span><span class="sxs-lookup"><span data-stu-id="f0b4e-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="f0b4e-110">Ottiene un valore che indica se questo `ICorDebugBreakpoint` è attiva.</span><span class="sxs-lookup"><span data-stu-id="f0b4e-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0b4e-111">Note</span><span class="sxs-lookup"><span data-stu-id="f0b4e-111">Remarks</span></span>  
 <span data-ttu-id="f0b4e-112">I punti di interruzione non supportano direttamente le espressioni condizionali.</span><span class="sxs-lookup"><span data-stu-id="f0b4e-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="f0b4e-113">Se si desidera tale funzionalità, un debugger deve implementarla in cima `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="f0b4e-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="f0b4e-114">Estende l'interfaccia ICorDebugFunctionBreakpoint `ICorDebugBreakpoint` per supportare i punti di interruzione all'interno di funzioni.</span><span class="sxs-lookup"><span data-stu-id="f0b4e-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0b4e-115">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="f0b4e-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0b4e-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f0b4e-116">Requirements</span></span>  
 <span data-ttu-id="f0b4e-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0b4e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0b4e-118">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="f0b4e-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0b4e-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0b4e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0b4e-120">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0b4e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0b4e-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0b4e-121">See Also</span></span>  
 [<span data-ttu-id="f0b4e-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="f0b4e-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

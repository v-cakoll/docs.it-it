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
ms.openlocfilehash: 53d8d219a13f2dade16a338efccf0837f8de0158
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784369"
---
# <a name="icordebugbreakpoint-interface"></a><span data-ttu-id="02ae5-102">Interfaccia ICorDebugBreakpoint</span><span class="sxs-lookup"><span data-stu-id="02ae5-102">ICorDebugBreakpoint Interface</span></span>

<span data-ttu-id="02ae5-103">Rappresenta un punto di interruzione in una funzione o un punto di controllo su un valore.</span><span class="sxs-lookup"><span data-stu-id="02ae5-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="02ae5-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="02ae5-104">Methods</span></span>  
  
|<span data-ttu-id="02ae5-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="02ae5-105">Method</span></span>|<span data-ttu-id="02ae5-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02ae5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="02ae5-107">Metodo Activate</span><span class="sxs-lookup"><span data-stu-id="02ae5-107">Activate Method</span></span>](icordebugbreakpoint-activate-method.md)|<span data-ttu-id="02ae5-108">Imposta lo stato attivo di questo `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="02ae5-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="02ae5-109">Metodo IsActive</span><span class="sxs-lookup"><span data-stu-id="02ae5-109">IsActive Method</span></span>](icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="02ae5-110">Ottiene un valore che indica se questo `ICorDebugBreakpoint` è attivo.</span><span class="sxs-lookup"><span data-stu-id="02ae5-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02ae5-111">Note</span><span class="sxs-lookup"><span data-stu-id="02ae5-111">Remarks</span></span>  
 <span data-ttu-id="02ae5-112">I punti di interruzione non supportano direttamente le espressioni condizionali.</span><span class="sxs-lookup"><span data-stu-id="02ae5-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="02ae5-113">Se si desidera questa funzionalità, un debugger deve implementarlo sopra `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="02ae5-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="02ae5-114">L'interfaccia ICorDebugFunctionBreakpoint estende `ICorDebugBreakpoint` per supportare i punti di interruzione all'interno di funzioni.</span><span class="sxs-lookup"><span data-stu-id="02ae5-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="02ae5-115">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="02ae5-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02ae5-116">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="02ae5-116">Requirements</span></span>  
 <span data-ttu-id="02ae5-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02ae5-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02ae5-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="02ae5-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02ae5-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02ae5-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02ae5-120">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02ae5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02ae5-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02ae5-121">See also</span></span>

- [<span data-ttu-id="02ae5-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="02ae5-122">Debugging Interfaces</span></span>](debugging-interfaces.md)

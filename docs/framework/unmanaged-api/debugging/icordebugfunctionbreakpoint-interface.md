---
title: Interfaccia ICorDebugFunctionBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugFunctionBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint
helpviewer_keywords:
- ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: 9c149303-14b1-4138-83d7-e8c3e0fcd332
topic_type:
- apiref
ms.openlocfilehash: 5e3804335bacefad61c4f521ea1ef1444b7b1fed
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777699"
---
# <a name="icordebugfunctionbreakpoint-interface"></a><span data-ttu-id="5662e-102">Interfaccia ICorDebugFunctionBreakpoint</span><span class="sxs-lookup"><span data-stu-id="5662e-102">ICorDebugFunctionBreakpoint Interface</span></span>

<span data-ttu-id="5662e-103">Estende l'interfaccia ICorDebugBreakpoint per supportare i punti di interruzione all'interno di funzioni.</span><span class="sxs-lookup"><span data-stu-id="5662e-103">Extends the ICorDebugBreakpoint interface to support breakpoints within functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5662e-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="5662e-104">Methods</span></span>  
  
|<span data-ttu-id="5662e-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="5662e-105">Method</span></span>|<span data-ttu-id="5662e-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5662e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5662e-107">Metodo GetFunction</span><span class="sxs-lookup"><span data-stu-id="5662e-107">GetFunction Method</span></span>](icordebugfunctionbreakpoint-getfunction-method.md)|<span data-ttu-id="5662e-108">Ottiene un puntatore a interfaccia a un ICorDebugFunction che fa riferimento alla funzione in cui è impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="5662e-108">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>|  
|[<span data-ttu-id="5662e-109">Metodo GetOffset</span><span class="sxs-lookup"><span data-stu-id="5662e-109">GetOffset Method</span></span>](icordebugfunctionbreakpoint-getoffset-method.md)|<span data-ttu-id="5662e-110">Ottiene l'offset del punto di interruzione all'interno della funzione.</span><span class="sxs-lookup"><span data-stu-id="5662e-110">Gets the offset of the breakpoint within the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5662e-111">Note</span><span class="sxs-lookup"><span data-stu-id="5662e-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5662e-112">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="5662e-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5662e-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="5662e-113">Requirements</span></span>  
 <span data-ttu-id="5662e-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5662e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5662e-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5662e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5662e-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5662e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5662e-117">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5662e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5662e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5662e-118">See also</span></span>

- [<span data-ttu-id="5662e-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="5662e-119">Debugging Interfaces</span></span>](debugging-interfaces.md)

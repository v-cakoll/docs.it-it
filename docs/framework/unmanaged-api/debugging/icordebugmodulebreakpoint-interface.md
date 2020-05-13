---
title: Interfaccia ICorDebugModuleBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugModuleBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleBreakpoint
helpviewer_keywords:
- ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: 34667162-f314-475f-ae1b-ce9cb0fcbb83
topic_type:
- apiref
ms.openlocfilehash: 7026d135b02563b6c718be4096d2c5cad9d33cec
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212282"
---
# <a name="icordebugmodulebreakpoint-interface"></a><span data-ttu-id="1be96-102">Interfaccia ICorDebugModuleBreakpoint</span><span class="sxs-lookup"><span data-stu-id="1be96-102">ICorDebugModuleBreakpoint Interface</span></span>

<span data-ttu-id="1be96-103">Consente di accedere a moduli specifici.</span><span class="sxs-lookup"><span data-stu-id="1be96-103">Provides access to specific modules.</span></span> <span data-ttu-id="1be96-104">Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugBreakpoint.</span><span class="sxs-lookup"><span data-stu-id="1be96-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1be96-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="1be96-105">Methods</span></span>  
  
|<span data-ttu-id="1be96-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="1be96-106">Method</span></span>|<span data-ttu-id="1be96-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1be96-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1be96-108">Metodo GetModule</span><span class="sxs-lookup"><span data-stu-id="1be96-108">GetModule Method</span></span>](icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="1be96-109">Ottiene un puntatore a interfaccia a un ICorDebugModule che fa riferimento al modulo in cui è impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="1be96-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1be96-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="1be96-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1be96-111">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="1be96-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1be96-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1be96-112">Requirements</span></span>  
 <span data-ttu-id="1be96-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1be96-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1be96-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1be96-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1be96-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1be96-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1be96-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1be96-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1be96-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1be96-117">See also</span></span>

- [<span data-ttu-id="1be96-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="1be96-118">Debugging Interfaces</span></span>](debugging-interfaces.md)

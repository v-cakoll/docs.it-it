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
ms.openlocfilehash: df3ad3fa4ef4eeee7e23ca1629da7a8b8ce09711
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792916"
---
# <a name="icordebugmodulebreakpoint-interface"></a><span data-ttu-id="efdd9-102">Interfaccia ICorDebugModuleBreakpoint</span><span class="sxs-lookup"><span data-stu-id="efdd9-102">ICorDebugModuleBreakpoint Interface</span></span>

<span data-ttu-id="efdd9-103">Consente di accedere a moduli specifici.</span><span class="sxs-lookup"><span data-stu-id="efdd9-103">Provides access to specific modules.</span></span> <span data-ttu-id="efdd9-104">Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugBreakpoint.</span><span class="sxs-lookup"><span data-stu-id="efdd9-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="efdd9-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="efdd9-105">Methods</span></span>  
  
|<span data-ttu-id="efdd9-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="efdd9-106">Method</span></span>|<span data-ttu-id="efdd9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="efdd9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="efdd9-108">Metodo GetModule</span><span class="sxs-lookup"><span data-stu-id="efdd9-108">GetModule Method</span></span>](icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="efdd9-109">Ottiene un puntatore a interfaccia a un ICorDebugModule che fa riferimento al modulo in cui è impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="efdd9-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="efdd9-110">Note</span><span class="sxs-lookup"><span data-stu-id="efdd9-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="efdd9-111">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="efdd9-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efdd9-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="efdd9-112">Requirements</span></span>  
 <span data-ttu-id="efdd9-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efdd9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efdd9-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="efdd9-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="efdd9-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="efdd9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="efdd9-116">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efdd9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efdd9-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="efdd9-117">See also</span></span>

- [<span data-ttu-id="efdd9-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="efdd9-118">Debugging Interfaces</span></span>](debugging-interfaces.md)

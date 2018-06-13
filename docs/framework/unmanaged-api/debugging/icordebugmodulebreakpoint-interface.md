---
title: ICorDebugModuleBreakpoint Interface1
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c04d5f779306a67e389f768cefdf633f3d72f0ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416137"
---
# <a name="icordebugmodulebreakpoint-interface1"></a><span data-ttu-id="81266-102">ICorDebugModuleBreakpoint Interface1</span><span class="sxs-lookup"><span data-stu-id="81266-102">ICorDebugModuleBreakpoint Interface1</span></span>
<span data-ttu-id="81266-103">Fornisce l'accesso a moduli specifici.</span><span class="sxs-lookup"><span data-stu-id="81266-103">Provides access to specific modules.</span></span> <span data-ttu-id="81266-104">Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugBreakpoint.</span><span class="sxs-lookup"><span data-stu-id="81266-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="81266-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="81266-105">Methods</span></span>  
  
|<span data-ttu-id="81266-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="81266-106">Method</span></span>|<span data-ttu-id="81266-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="81266-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="81266-108">Metodo GetModule</span><span class="sxs-lookup"><span data-stu-id="81266-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="81266-109">Ottiene un puntatore a interfaccia a un ICorDebugModule che fa riferimento al modulo in cui è impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="81266-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81266-110">Note</span><span class="sxs-lookup"><span data-stu-id="81266-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="81266-111">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="81266-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81266-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="81266-112">Requirements</span></span>  
 <span data-ttu-id="81266-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81266-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81266-114">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="81266-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="81266-115">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="81266-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81266-116">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81266-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81266-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81266-117">See Also</span></span>  
 [<span data-ttu-id="81266-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="81266-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

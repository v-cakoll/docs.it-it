---
title: ICorDebugModuleBreakpoint Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModuleBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModuleBreakpoint
helpviewer_keywords: ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: 34667162-f314-475f-ae1b-ce9cb0fcbb83
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3e3937c6c0baef4cc927b5c5d789826c70beebf2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodulebreakpoint-interface1"></a><span data-ttu-id="84652-102">ICorDebugModuleBreakpoint Interface1</span><span class="sxs-lookup"><span data-stu-id="84652-102">ICorDebugModuleBreakpoint Interface1</span></span>
<span data-ttu-id="84652-103">Fornisce l'accesso a moduli specifici.</span><span class="sxs-lookup"><span data-stu-id="84652-103">Provides access to specific modules.</span></span> <span data-ttu-id="84652-104">Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugBreakpoint.</span><span class="sxs-lookup"><span data-stu-id="84652-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="84652-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="84652-105">Methods</span></span>  
  
|<span data-ttu-id="84652-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="84652-106">Method</span></span>|<span data-ttu-id="84652-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84652-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="84652-108">GetModule (metodo)</span><span class="sxs-lookup"><span data-stu-id="84652-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="84652-109">Ottiene un puntatore a interfaccia a un ICorDebugModule che fa riferimento al modulo in cui è impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="84652-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84652-110">Note</span><span class="sxs-lookup"><span data-stu-id="84652-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84652-111">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="84652-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84652-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="84652-112">Requirements</span></span>  
 <span data-ttu-id="84652-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84652-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84652-114">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="84652-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84652-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84652-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84652-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84652-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84652-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84652-117">See Also</span></span>  
 [<span data-ttu-id="84652-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="84652-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

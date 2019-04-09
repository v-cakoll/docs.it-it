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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d6a43a264fcaa94ce4e629d8db504e9d416f6b89
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59179712"
---
# <a name="icordebugmodulebreakpoint-interface"></a><span data-ttu-id="98e19-102">Interfaccia ICorDebugModuleBreakpoint</span><span class="sxs-lookup"><span data-stu-id="98e19-102">ICorDebugModuleBreakpoint Interface</span></span>

<span data-ttu-id="98e19-103">Fornisce l'accesso a moduli specifici.</span><span class="sxs-lookup"><span data-stu-id="98e19-103">Provides access to specific modules.</span></span> <span data-ttu-id="98e19-104">Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugBreakpoint.</span><span class="sxs-lookup"><span data-stu-id="98e19-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="98e19-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="98e19-105">Methods</span></span>  
  
|<span data-ttu-id="98e19-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="98e19-106">Method</span></span>|<span data-ttu-id="98e19-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="98e19-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="98e19-108">Metodo GetModule</span><span class="sxs-lookup"><span data-stu-id="98e19-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="98e19-109">Ottiene un puntatore a interfaccia per un ICorDebugModule che fa riferimento al modulo in cui è impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="98e19-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98e19-110">Note</span><span class="sxs-lookup"><span data-stu-id="98e19-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="98e19-111">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="98e19-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98e19-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="98e19-112">Requirements</span></span>  
 <span data-ttu-id="98e19-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98e19-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98e19-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="98e19-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98e19-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98e19-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="98e19-116">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="98e19-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="98e19-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98e19-117">See also</span></span>

- [<span data-ttu-id="98e19-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="98e19-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

---
title: Interfaccia ICorDebugValueBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugValueBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueBreakpoint
helpviewer_keywords:
- ICorDebugValueBreakpoint interface [.NET Framework debugging]
ms.assetid: c02338fe-da6c-467f-9567-70ebb387e901
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 778359a7d26b6e2f19984a1f7ff06a527f2449f0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59167746"
---
# <a name="icordebugvaluebreakpoint-interface"></a><span data-ttu-id="55ce0-102">Interfaccia ICorDebugValueBreakpoint</span><span class="sxs-lookup"><span data-stu-id="55ce0-102">ICorDebugValueBreakpoint Interface</span></span>
<span data-ttu-id="55ce0-103">Estende l'interfaccia ICorDebugBreakpoint per fornire l'accesso a valori specifici.</span><span class="sxs-lookup"><span data-stu-id="55ce0-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="55ce0-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="55ce0-104">Methods</span></span>  
  
|<span data-ttu-id="55ce0-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="55ce0-105">Method</span></span>|<span data-ttu-id="55ce0-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="55ce0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="55ce0-107">Metodo GetValue</span><span class="sxs-lookup"><span data-stu-id="55ce0-107">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="55ce0-108">Ottiene un puntatore a interfaccia a un oggetto ICorDebugValue che rappresenta il valore dell'oggetto su cui è impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="55ce0-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55ce0-109">Note</span><span class="sxs-lookup"><span data-stu-id="55ce0-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="55ce0-110">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="55ce0-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55ce0-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="55ce0-111">Requirements</span></span>  
 <span data-ttu-id="55ce0-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55ce0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55ce0-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="55ce0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="55ce0-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55ce0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55ce0-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55ce0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55ce0-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55ce0-116">See also</span></span>

- [<span data-ttu-id="55ce0-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="55ce0-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

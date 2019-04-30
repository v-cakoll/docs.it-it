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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993721"
---
# <a name="icordebugvaluebreakpoint-interface"></a><span data-ttu-id="1edad-102">Interfaccia ICorDebugValueBreakpoint</span><span class="sxs-lookup"><span data-stu-id="1edad-102">ICorDebugValueBreakpoint Interface</span></span>
<span data-ttu-id="1edad-103">Estende l'interfaccia ICorDebugBreakpoint per fornire l'accesso a valori specifici.</span><span class="sxs-lookup"><span data-stu-id="1edad-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1edad-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="1edad-104">Methods</span></span>  
  
|<span data-ttu-id="1edad-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="1edad-105">Method</span></span>|<span data-ttu-id="1edad-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1edad-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1edad-107">Metodo GetValue</span><span class="sxs-lookup"><span data-stu-id="1edad-107">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="1edad-108">Ottiene un puntatore a interfaccia a un oggetto ICorDebugValue che rappresenta il valore dell'oggetto su cui è impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="1edad-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1edad-109">Note</span><span class="sxs-lookup"><span data-stu-id="1edad-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1edad-110">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="1edad-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1edad-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1edad-111">Requirements</span></span>  
 <span data-ttu-id="1edad-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1edad-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1edad-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1edad-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1edad-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1edad-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1edad-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1edad-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1edad-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1edad-116">See also</span></span>

- [<span data-ttu-id="1edad-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="1edad-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

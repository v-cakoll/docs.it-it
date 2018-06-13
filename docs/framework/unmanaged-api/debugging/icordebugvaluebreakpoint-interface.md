---
title: ICorDebugValueBreakpoint Interface1
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
ms.openlocfilehash: fbb0479ee9d14b534e419c74560f4da527884246
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419052"
---
# <a name="icordebugvaluebreakpoint-interface1"></a><span data-ttu-id="cddb6-102">ICorDebugValueBreakpoint Interface1</span><span class="sxs-lookup"><span data-stu-id="cddb6-102">ICorDebugValueBreakpoint Interface1</span></span>
<span data-ttu-id="cddb6-103">Estende l'interfaccia ICorDebugBreakpoint per fornire l'accesso a valori specifici.</span><span class="sxs-lookup"><span data-stu-id="cddb6-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cddb6-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="cddb6-104">Methods</span></span>  
  
|<span data-ttu-id="cddb6-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="cddb6-105">Method</span></span>|<span data-ttu-id="cddb6-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cddb6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cddb6-107">Metodo GetValue</span><span class="sxs-lookup"><span data-stu-id="cddb6-107">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="cddb6-108">Ottiene un puntatore a interfaccia a un oggetto ICorDebugValue che rappresenta il valore dell'oggetto su cui è impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="cddb6-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cddb6-109">Note</span><span class="sxs-lookup"><span data-stu-id="cddb6-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cddb6-110">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="cddb6-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cddb6-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cddb6-111">Requirements</span></span>  
 <span data-ttu-id="cddb6-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cddb6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cddb6-113">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="cddb6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cddb6-114">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="cddb6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cddb6-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cddb6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cddb6-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cddb6-116">See Also</span></span>  
 [<span data-ttu-id="cddb6-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="cddb6-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

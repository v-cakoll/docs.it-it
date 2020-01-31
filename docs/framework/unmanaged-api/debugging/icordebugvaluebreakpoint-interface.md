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
ms.openlocfilehash: e1bb5a6fd0550f7c25d46fa31ca11a10cec54986
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791081"
---
# <a name="icordebugvaluebreakpoint-interface"></a><span data-ttu-id="a017a-102">Interfaccia ICorDebugValueBreakpoint</span><span class="sxs-lookup"><span data-stu-id="a017a-102">ICorDebugValueBreakpoint Interface</span></span>
<span data-ttu-id="a017a-103">Estende l'interfaccia ICorDebugBreakpoint per fornire l'accesso a valori specifici.</span><span class="sxs-lookup"><span data-stu-id="a017a-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a017a-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="a017a-104">Methods</span></span>  
  
|<span data-ttu-id="a017a-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="a017a-105">Method</span></span>|<span data-ttu-id="a017a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a017a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a017a-107">Metodo GetValue</span><span class="sxs-lookup"><span data-stu-id="a017a-107">GetValue Method</span></span>](icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="a017a-108">Ottiene un puntatore a interfaccia a un oggetto ICorDebugValue che rappresenta il valore dell'oggetto su cui è impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="a017a-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a017a-109">Note</span><span class="sxs-lookup"><span data-stu-id="a017a-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a017a-110">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="a017a-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a017a-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="a017a-111">Requirements</span></span>  
 <span data-ttu-id="a017a-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a017a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a017a-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a017a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a017a-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a017a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a017a-115">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a017a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a017a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a017a-116">See also</span></span>

- [<span data-ttu-id="a017a-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a017a-117">Debugging Interfaces</span></span>](debugging-interfaces.md)

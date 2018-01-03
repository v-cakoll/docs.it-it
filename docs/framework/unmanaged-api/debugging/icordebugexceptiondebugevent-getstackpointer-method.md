---
title: Metodo ICorDebugExceptionDebugEvent::GetStackPointer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: d8f66a1c-16be-4264-afc5-bc2dfbb4a682
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1b9096bbb494036156a528d8f9e940630f555f6a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugexceptiondebugeventgetstackpointer-method"></a><span data-ttu-id="7076d-102">Metodo ICorDebugExceptionDebugEvent::GetStackPointer</span><span class="sxs-lookup"><span data-stu-id="7076d-102">ICorDebugExceptionDebugEvent::GetStackPointer Method</span></span>
<span data-ttu-id="7076d-103">Ottiene il puntatore dello stack per questo evento di debug per le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="7076d-103">Gets the stack pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7076d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7076d-104">Syntax</span></span>  
  
```  
HRESULT GetStackPointer(  
   [out]CORDB_ADDRESS *pStackPointer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7076d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7076d-105">Parameters</span></span>  
 `pStackPointer`  
 <span data-ttu-id="7076d-106">[out] Puntatore all'indirizzo del puntatore dello stack per l'attuale evento di debug per le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="7076d-106">[out] A pointer to the address of the stack pointer for this exception debug event.</span></span> <span data-ttu-id="7076d-107">Per altre informazioni, vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="7076d-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7076d-108">Note</span><span class="sxs-lookup"><span data-stu-id="7076d-108">Remarks</span></span>  
 <span data-ttu-id="7076d-109">Il significato di questo puntatore dello stack dipende dal tipo di evento, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="7076d-109">The meaning of this stack pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="7076d-110">Tipo evento</span><span class="sxs-lookup"><span data-stu-id="7076d-110">Event type</span></span>|<span data-ttu-id="7076d-111">Significato del valore `pStackPointer`</span><span class="sxs-lookup"><span data-stu-id="7076d-111">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="7076d-112">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="7076d-112">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="7076d-113">Puntatore dello stack per il frame che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="7076d-113">The stack pointer for the frame that threw the exception.</span></span>|  
|[<span data-ttu-id="7076d-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="7076d-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="7076d-115">Puntatore dello stack per il frame di codice utente più vicino al punto dell'eccezione generata.</span><span class="sxs-lookup"><span data-stu-id="7076d-115">The stack pointer for the user-code frame closest to the point of the thrown exception.</span></span>|  
|[<span data-ttu-id="7076d-116">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="7076d-116">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="7076d-117">Puntatore dello stack per il frame che contiene il gestore catch.</span><span class="sxs-lookup"><span data-stu-id="7076d-117">The stack pointer for the frame that contains the catch handler.</span></span>|  
|[<span data-ttu-id="7076d-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="7076d-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="7076d-119">`pStackPointer` è **null**.</span><span class="sxs-lookup"><span data-stu-id="7076d-119">`pStackPointer` is **null**.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="7076d-120">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="7076d-120">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="7076d-121">Il tipo di evento è disponibile il [icordebugdebugevent:: Geteventkind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="7076d-121">The event type is available from the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7076d-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7076d-122">Requirements</span></span>  
 <span data-ttu-id="7076d-123">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7076d-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7076d-124">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="7076d-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7076d-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7076d-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7076d-126">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7076d-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7076d-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7076d-127">See Also</span></span>  
 [<span data-ttu-id="7076d-128">Interfaccia ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="7076d-128">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
 [<span data-ttu-id="7076d-129">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="7076d-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

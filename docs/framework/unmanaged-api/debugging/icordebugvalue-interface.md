---
title: Interfaccia ICorDebugValue
ms.date: 03/30/2017
api_name:
- ICorDebugValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue
helpviewer_keywords:
- ICorDebugValue interface [.NET Framework debugging]
ms.assetid: b2f7007f-c446-4b18-aed1-a25cff8aee31
topic_type:
- apiref
ms.openlocfilehash: e1044386bd6251132703c4e98a0cf2ed267d34e0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791142"
---
# <a name="icordebugvalue-interface"></a><span data-ttu-id="ee63d-102">Interfaccia ICorDebugValue</span><span class="sxs-lookup"><span data-stu-id="ee63d-102">ICorDebugValue Interface</span></span>
<span data-ttu-id="ee63d-103">Rappresenta un valore nel processo di cui è in corso il debug.</span><span class="sxs-lookup"><span data-stu-id="ee63d-103">Represents a value in the process being debugged.</span></span> <span data-ttu-id="ee63d-104">Il valore può essere un valore di lettura o di scrittura.</span><span class="sxs-lookup"><span data-stu-id="ee63d-104">The value can be a read or a write value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ee63d-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="ee63d-105">Methods</span></span>  
  
|<span data-ttu-id="ee63d-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="ee63d-106">Method</span></span>|<span data-ttu-id="ee63d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ee63d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ee63d-108">Metodo CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ee63d-108">CreateBreakpoint Method</span></span>](icordebugvalue-createbreakpoint-method.md)|<span data-ttu-id="ee63d-109">Non è attualmente implementato.</span><span class="sxs-lookup"><span data-stu-id="ee63d-109">This method is not currently implemented.</span></span>|  
|[<span data-ttu-id="ee63d-110">Metodo GetAddress</span><span class="sxs-lookup"><span data-stu-id="ee63d-110">GetAddress Method</span></span>](icordebugvalue-getaddress-method.md)|<span data-ttu-id="ee63d-111">Ottiene l'indirizzo di questo `ICorDebugValue` oggetto, che è in fase di debug.</span><span class="sxs-lookup"><span data-stu-id="ee63d-111">Gets the address of this `ICorDebugValue` object, which is in the process of being debugged.</span></span>|  
|[<span data-ttu-id="ee63d-112">Metodo GetSize</span><span class="sxs-lookup"><span data-stu-id="ee63d-112">GetSize Method</span></span>](icordebugvalue-getsize-method.md)|<span data-ttu-id="ee63d-113">Ottiene le dimensioni in byte di questo oggetto `ICorDebugValue`.</span><span class="sxs-lookup"><span data-stu-id="ee63d-113">Gets the size, in bytes, of this `ICorDebugValue` object.</span></span>|  
|[<span data-ttu-id="ee63d-114">Metodo GetType</span><span class="sxs-lookup"><span data-stu-id="ee63d-114">GetType Method</span></span>](icordebugvalue-gettype-method.md)|<span data-ttu-id="ee63d-115">Ottiene il tipo primitivo di questo oggetto `ICorDebugValue`.</span><span class="sxs-lookup"><span data-stu-id="ee63d-115">Gets the primitive type of this `ICorDebugValue` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee63d-116">Note</span><span class="sxs-lookup"><span data-stu-id="ee63d-116">Remarks</span></span>  
 <span data-ttu-id="ee63d-117">In generale, la proprietà di un oggetto valore viene passata quando viene restituito.</span><span class="sxs-lookup"><span data-stu-id="ee63d-117">In general, ownership of a value object is passed when it is returned.</span></span> <span data-ttu-id="ee63d-118">Il destinatario è responsabile della rimozione di un riferimento dall'oggetto al termine dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="ee63d-118">The recipient is responsible for removing a reference from the object when it is finished with the object.</span></span>  
  
 <span data-ttu-id="ee63d-119">A seconda della posizione in cui è stato recuperato il valore, il valore potrebbe non rimanere valido dopo la ripresa del processo.</span><span class="sxs-lookup"><span data-stu-id="ee63d-119">Depending on where the value was retrieved from, the value may not remain valid after the process is resumed.</span></span> <span data-ttu-id="ee63d-120">Pertanto, in generale, il valore non deve essere mantenuto in una chiamata al metodo [ICorDebugController:: continue](icordebugcontroller-continue-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ee63d-120">So, in general, the value shouldn't be held across a call of the [ICorDebugController::Continue](icordebugcontroller-continue-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ee63d-121">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="ee63d-121">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee63d-122">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="ee63d-122">Requirements</span></span>  
 <span data-ttu-id="ee63d-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee63d-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee63d-124">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ee63d-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee63d-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee63d-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee63d-126">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee63d-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee63d-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee63d-127">See also</span></span>

- [<span data-ttu-id="ee63d-128">Interfaccia ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="ee63d-128">ICorDebugValue3 Interface</span></span>](icordebugvalue3-interface.md)
- [<span data-ttu-id="ee63d-129">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="ee63d-129">Debugging Interfaces</span></span>](debugging-interfaces.md)

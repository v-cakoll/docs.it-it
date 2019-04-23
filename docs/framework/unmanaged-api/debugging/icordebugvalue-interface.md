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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bdc889dd6b2854654bfe43b24afbe4cc19863c80
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59227821"
---
# <a name="icordebugvalue-interface"></a><span data-ttu-id="84a2e-102">Interfaccia ICorDebugValue</span><span class="sxs-lookup"><span data-stu-id="84a2e-102">ICorDebugValue Interface</span></span>
<span data-ttu-id="84a2e-103">Rappresenta un valore nel processo sottoposto a debug.</span><span class="sxs-lookup"><span data-stu-id="84a2e-103">Represents a value in the process being debugged.</span></span> <span data-ttu-id="84a2e-104">Il valore può essere un'operazione di lettura o di scrittura.</span><span class="sxs-lookup"><span data-stu-id="84a2e-104">The value can be a read or a write value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="84a2e-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="84a2e-105">Methods</span></span>  
  
|<span data-ttu-id="84a2e-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="84a2e-106">Method</span></span>|<span data-ttu-id="84a2e-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84a2e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="84a2e-108">Metodo CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="84a2e-108">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-createbreakpoint-method.md)|<span data-ttu-id="84a2e-109">Questo metodo non è attualmente implementato.</span><span class="sxs-lookup"><span data-stu-id="84a2e-109">This method is not currently implemented.</span></span>|  
|[<span data-ttu-id="84a2e-110">Metodo GetAddress</span><span class="sxs-lookup"><span data-stu-id="84a2e-110">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)|<span data-ttu-id="84a2e-111">Ottiene l'indirizzo di questo `ICorDebugValue` oggetto, che è in corso in fase di debug.</span><span class="sxs-lookup"><span data-stu-id="84a2e-111">Gets the address of this `ICorDebugValue` object, which is in the process of being debugged.</span></span>|  
|[<span data-ttu-id="84a2e-112">Metodo GetSize</span><span class="sxs-lookup"><span data-stu-id="84a2e-112">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)|<span data-ttu-id="84a2e-113">Ottiene la dimensione, espressa in byte, di questo `ICorDebugValue` oggetto.</span><span class="sxs-lookup"><span data-stu-id="84a2e-113">Gets the size, in bytes, of this `ICorDebugValue` object.</span></span>|  
|[<span data-ttu-id="84a2e-114">Metodo GetType</span><span class="sxs-lookup"><span data-stu-id="84a2e-114">GetType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)|<span data-ttu-id="84a2e-115">Ottiene il tipo primitivo di questo `ICorDebugValue` oggetto.</span><span class="sxs-lookup"><span data-stu-id="84a2e-115">Gets the primitive type of this `ICorDebugValue` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84a2e-116">Note</span><span class="sxs-lookup"><span data-stu-id="84a2e-116">Remarks</span></span>  
 <span data-ttu-id="84a2e-117">In generale, la proprietà di un oggetto valore viene passata quando viene restituita.</span><span class="sxs-lookup"><span data-stu-id="84a2e-117">In general, ownership of a value object is passed when it is returned.</span></span> <span data-ttu-id="84a2e-118">Il destinatario è responsabile della rimozione di un riferimento dall'oggetto quando viene terminato con l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="84a2e-118">The recipient is responsible for removing a reference from the object when it is finished with the object.</span></span>  
  
 <span data-ttu-id="84a2e-119">A seconda di dove il valore è stato recuperato da, il valore non restino valido dopo il processo viene ripreso.</span><span class="sxs-lookup"><span data-stu-id="84a2e-119">Depending on where the value was retrieved from, the value may not remain valid after the process is resumed.</span></span> <span data-ttu-id="84a2e-120">Pertanto, in generale, il valore non deve essere mantenuto in una chiamata del [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="84a2e-120">So, in general, the value shouldn't be held across a call of the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84a2e-121">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="84a2e-121">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84a2e-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="84a2e-122">Requirements</span></span>  
 <span data-ttu-id="84a2e-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84a2e-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84a2e-124">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84a2e-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84a2e-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84a2e-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84a2e-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84a2e-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84a2e-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84a2e-127">See also</span></span>

- [<span data-ttu-id="84a2e-128">Interfaccia ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="84a2e-128">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
- [<span data-ttu-id="84a2e-129">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="84a2e-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

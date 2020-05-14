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
ms.openlocfilehash: b8d2e49031e59db0527de3c848d7d390095797bf
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396783"
---
# <a name="icordebugvalue-interface"></a><span data-ttu-id="ca207-102">Interfaccia ICorDebugValue</span><span class="sxs-lookup"><span data-stu-id="ca207-102">ICorDebugValue Interface</span></span>
<span data-ttu-id="ca207-103">Rappresenta un valore nel processo di cui è in corso il debug.</span><span class="sxs-lookup"><span data-stu-id="ca207-103">Represents a value in the process being debugged.</span></span> <span data-ttu-id="ca207-104">Il valore può essere un valore di lettura o di scrittura.</span><span class="sxs-lookup"><span data-stu-id="ca207-104">The value can be a read or a write value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ca207-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="ca207-105">Methods</span></span>  
  
|<span data-ttu-id="ca207-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="ca207-106">Method</span></span>|<span data-ttu-id="ca207-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ca207-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ca207-108">Metodo CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ca207-108">CreateBreakpoint Method</span></span>](icordebugvalue-createbreakpoint-method.md)|<span data-ttu-id="ca207-109">Non è attualmente implementato.</span><span class="sxs-lookup"><span data-stu-id="ca207-109">This method is not currently implemented.</span></span>|  
|[<span data-ttu-id="ca207-110">Metodo GetAddress</span><span class="sxs-lookup"><span data-stu-id="ca207-110">GetAddress Method</span></span>](icordebugvalue-getaddress-method.md)|<span data-ttu-id="ca207-111">Ottiene l'indirizzo di questo `ICorDebugValue` oggetto, che è in fase di debug.</span><span class="sxs-lookup"><span data-stu-id="ca207-111">Gets the address of this `ICorDebugValue` object, which is in the process of being debugged.</span></span>|  
|[<span data-ttu-id="ca207-112">Metodo GetSize</span><span class="sxs-lookup"><span data-stu-id="ca207-112">GetSize Method</span></span>](icordebugvalue-getsize-method.md)|<span data-ttu-id="ca207-113">Ottiene le dimensioni in byte di questo `ICorDebugValue` oggetto.</span><span class="sxs-lookup"><span data-stu-id="ca207-113">Gets the size, in bytes, of this `ICorDebugValue` object.</span></span>|  
|[<span data-ttu-id="ca207-114">Metodo GetType</span><span class="sxs-lookup"><span data-stu-id="ca207-114">GetType Method</span></span>](icordebugvalue-gettype-method.md)|<span data-ttu-id="ca207-115">Ottiene il tipo primitivo di questo `ICorDebugValue` oggetto.</span><span class="sxs-lookup"><span data-stu-id="ca207-115">Gets the primitive type of this `ICorDebugValue` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca207-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="ca207-116">Remarks</span></span>  
 <span data-ttu-id="ca207-117">In generale, la proprietà di un oggetto valore viene passata quando viene restituito.</span><span class="sxs-lookup"><span data-stu-id="ca207-117">In general, ownership of a value object is passed when it is returned.</span></span> <span data-ttu-id="ca207-118">Il destinatario è responsabile della rimozione di un riferimento dall'oggetto al termine dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="ca207-118">The recipient is responsible for removing a reference from the object when it is finished with the object.</span></span>  
  
 <span data-ttu-id="ca207-119">A seconda della posizione in cui è stato recuperato il valore, il valore potrebbe non rimanere valido dopo la ripresa del processo.</span><span class="sxs-lookup"><span data-stu-id="ca207-119">Depending on where the value was retrieved from, the value may not remain valid after the process is resumed.</span></span> <span data-ttu-id="ca207-120">Pertanto, in generale, il valore non deve essere mantenuto in una chiamata al metodo [ICorDebugController:: continue](icordebugcontroller-continue-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ca207-120">So, in general, the value shouldn't be held across a call of the [ICorDebugController::Continue](icordebugcontroller-continue-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ca207-121">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="ca207-121">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca207-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ca207-122">Requirements</span></span>  
 <span data-ttu-id="ca207-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca207-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca207-124">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ca207-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca207-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca207-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca207-126">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca207-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca207-127">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="ca207-127">See also</span></span>

- [<span data-ttu-id="ca207-128">Interfaccia ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="ca207-128">ICorDebugValue3 Interface</span></span>](icordebugvalue3-interface.md)
- [<span data-ttu-id="ca207-129">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="ca207-129">Debugging Interfaces</span></span>](debugging-interfaces.md)

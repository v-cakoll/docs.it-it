---
title: Interfaccia1 ICorDebugReferenceValue
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue
helpviewer_keywords:
- ICorDebugReferenceValue interface [.NET Framework debugging]
ms.assetid: 2040e2be-119a-4cfb-ae52-b0b6f052665c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3dbe5388d7c18202f4b89269141d33463edb07a4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54544273"
---
# <a name="icordebugreferencevalue-interface1"></a><span data-ttu-id="e94f6-102">Interfaccia1 ICorDebugReferenceValue</span><span class="sxs-lookup"><span data-stu-id="e94f6-102">ICorDebugReferenceValue Interface1</span></span>
<span data-ttu-id="e94f6-103">Fornisce metodi che gestiscono un valore che è un riferimento a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="e94f6-103">Provides methods that manage a value that is a reference to an object.</span></span> <span data-ttu-id="e94f6-104">(Vale a dire, questa interfaccia fornisce metodi che gestiscono un puntatore.) Questa interfaccia implementerà "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="e94f6-104">(That is, this interface provides methods that manage a pointer.) This interface implements "ICorDebugValue".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e94f6-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="e94f6-105">Methods</span></span>  
  
|<span data-ttu-id="e94f6-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="e94f6-106">Method</span></span>|<span data-ttu-id="e94f6-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e94f6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e94f6-108">Metodo Dereference</span><span class="sxs-lookup"><span data-stu-id="e94f6-108">Dereference Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereference-method.md)|<span data-ttu-id="e94f6-109">Ottiene l'oggetto a cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="e94f6-109">Gets the object that is referenced.</span></span>|  
|[<span data-ttu-id="e94f6-110">Metodo DereferenceStrong</span><span class="sxs-lookup"><span data-stu-id="e94f6-110">DereferenceStrong Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereferencestrong-method.md)|<span data-ttu-id="e94f6-111">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="e94f6-111">Not implemented.</span></span> <span data-ttu-id="e94f6-112">Non chiamare questo metodo.</span><span class="sxs-lookup"><span data-stu-id="e94f6-112">Do not call this method.</span></span>|  
|[<span data-ttu-id="e94f6-113">Metodo GetValue</span><span class="sxs-lookup"><span data-stu-id="e94f6-113">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-getvalue-method.md)|<span data-ttu-id="e94f6-114">Ottiene l'indirizzo di memoria corrente dell'oggetto di riferimento.</span><span class="sxs-lookup"><span data-stu-id="e94f6-114">Gets the current memory address of the referenced object.</span></span>|  
|[<span data-ttu-id="e94f6-115">Metodo IsNull</span><span class="sxs-lookup"><span data-stu-id="e94f6-115">IsNull Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-isnull-method.md)|<span data-ttu-id="e94f6-116">Ottiene un valore che indica se questo `ICorDebugReferenceValue` è un valore null, nel qual caso il `ICorDebugReferenceValue` non punta a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="e94f6-116">Gets a value that indicates whether this `ICorDebugReferenceValue` is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>|  
|[<span data-ttu-id="e94f6-117">Metodo SetValue</span><span class="sxs-lookup"><span data-stu-id="e94f6-117">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-setvalue-method.md)|<span data-ttu-id="e94f6-118">Imposta l'indirizzo di memoria corrente.</span><span class="sxs-lookup"><span data-stu-id="e94f6-118">Sets the current memory address.</span></span> <span data-ttu-id="e94f6-119">Vale a dire, questo metodo imposta `ICorDebugReferenceValue` in modo che punti a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="e94f6-119">That is, this method sets this `ICorDebugReferenceValue` to point to an object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e94f6-120">Note</span><span class="sxs-lookup"><span data-stu-id="e94f6-120">Remarks</span></span>  
 <span data-ttu-id="e94f6-121">Common language runtime (CLR) può effettuare un'operazione di garbage collection sugli oggetti quando continua il processo sottoposto a debug.</span><span class="sxs-lookup"><span data-stu-id="e94f6-121">The common language runtime (CLR) may do a garbage collection on objects when the debugged process is continued.</span></span> <span data-ttu-id="e94f6-122">La garbage collection potrebbe spostare gli oggetti in memoria.</span><span class="sxs-lookup"><span data-stu-id="e94f6-122">The garbage collection may move objects around in memory.</span></span> <span data-ttu-id="e94f6-123">Un `ICorDebugReferenceValue` interagirà con l'operazione di garbage collection in modo che le relative informazioni viene aggiornate dopo l'operazione di garbage collection o verrà invalidato in modo implicito prima dell'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="e94f6-123">An `ICorDebugReferenceValue` will either cooperate with the garbage collection so that its information is updated after the garbage collection, or it will be invalidated implicitly before the garbage collection.</span></span>  
  
 <span data-ttu-id="e94f6-124">Il `ICorDebugReferenceValue` oggetto può essere invalidato in modo implicito dopo il processo sottoposto a debug.</span><span class="sxs-lookup"><span data-stu-id="e94f6-124">The `ICorDebugReferenceValue` object may be implicitly invalidated after the debugged process has been continued.</span></span> <span data-ttu-id="e94f6-125">Fino a quando non viene rilasciata o esposti in modo esplicito, derivato "ICorDebugHandleValue" non viene invalidata.</span><span class="sxs-lookup"><span data-stu-id="e94f6-125">The derived "ICorDebugHandleValue" is not invalidated until it is explicitly released or exposed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e94f6-126">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="e94f6-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e94f6-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e94f6-127">Requirements</span></span>  
 <span data-ttu-id="e94f6-128">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e94f6-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e94f6-129">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e94f6-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e94f6-130">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e94f6-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e94f6-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e94f6-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e94f6-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e94f6-132">See also</span></span>


- [<span data-ttu-id="e94f6-133">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e94f6-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

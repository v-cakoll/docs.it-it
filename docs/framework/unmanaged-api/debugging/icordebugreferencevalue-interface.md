---
title: Interfaccia ICorDebugReferenceValue
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
ms.openlocfilehash: 67006603747abd89f1b635c065860dcbe1c47a29
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965638"
---
# <a name="icordebugreferencevalue-interface"></a><span data-ttu-id="03677-102">Interfaccia ICorDebugReferenceValue</span><span class="sxs-lookup"><span data-stu-id="03677-102">ICorDebugReferenceValue Interface</span></span>
<span data-ttu-id="03677-103">Fornisce metodi che gestiscono un valore che è un riferimento a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="03677-103">Provides methods that manage a value that is a reference to an object.</span></span> <span data-ttu-id="03677-104">(Ovvero, questa interfaccia fornisce metodi per la gestione di un puntatore). Questa interfaccia implementa "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="03677-104">(That is, this interface provides methods that manage a pointer.) This interface implements "ICorDebugValue".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="03677-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="03677-105">Methods</span></span>  
  
|<span data-ttu-id="03677-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="03677-106">Method</span></span>|<span data-ttu-id="03677-107">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="03677-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="03677-108">Metodo Dereference</span><span class="sxs-lookup"><span data-stu-id="03677-108">Dereference Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereference-method.md)|<span data-ttu-id="03677-109">Ottiene l'oggetto a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="03677-109">Gets the object that is referenced.</span></span>|  
|[<span data-ttu-id="03677-110">Metodo DereferenceStrong</span><span class="sxs-lookup"><span data-stu-id="03677-110">DereferenceStrong Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereferencestrong-method.md)|<span data-ttu-id="03677-111">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="03677-111">Not implemented.</span></span> <span data-ttu-id="03677-112">Non chiamare questo metodo.</span><span class="sxs-lookup"><span data-stu-id="03677-112">Do not call this method.</span></span>|  
|[<span data-ttu-id="03677-113">Metodo GetValue</span><span class="sxs-lookup"><span data-stu-id="03677-113">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-getvalue-method.md)|<span data-ttu-id="03677-114">Ottiene l'indirizzo di memoria corrente dell'oggetto a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="03677-114">Gets the current memory address of the referenced object.</span></span>|  
|[<span data-ttu-id="03677-115">Metodo IsNull</span><span class="sxs-lookup"><span data-stu-id="03677-115">IsNull Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-isnull-method.md)|<span data-ttu-id="03677-116">Ottiene un valore che indica se `ICorDebugReferenceValue` si tratta di un valore null, nel qual `ICorDebugReferenceValue` caso non punta a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="03677-116">Gets a value that indicates whether this `ICorDebugReferenceValue` is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>|  
|[<span data-ttu-id="03677-117">Metodo SetValue</span><span class="sxs-lookup"><span data-stu-id="03677-117">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-setvalue-method.md)|<span data-ttu-id="03677-118">Imposta l'indirizzo di memoria corrente.</span><span class="sxs-lookup"><span data-stu-id="03677-118">Sets the current memory address.</span></span> <span data-ttu-id="03677-119">Questo metodo imposta questa `ICorDebugReferenceValue` impostazione in modo che punti a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="03677-119">That is, this method sets this `ICorDebugReferenceValue` to point to an object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03677-120">Note</span><span class="sxs-lookup"><span data-stu-id="03677-120">Remarks</span></span>  
 <span data-ttu-id="03677-121">Il Common Language Runtime (CLR) può eseguire una Garbage Collection sugli oggetti quando il processo sottoposto a debug viene continuato.</span><span class="sxs-lookup"><span data-stu-id="03677-121">The common language runtime (CLR) may do a garbage collection on objects when the debugged process is continued.</span></span> <span data-ttu-id="03677-122">Il Garbage Collection può spostare gli oggetti in memoria.</span><span class="sxs-lookup"><span data-stu-id="03677-122">The garbage collection may move objects around in memory.</span></span> <span data-ttu-id="03677-123">Un `ICorDebugReferenceValue` oggetto collaborerà con l'Garbage Collection in modo che le informazioni vengano aggiornate dopo l'Garbage Collection oppure verranno invalidate in modo implicito prima del Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="03677-123">An `ICorDebugReferenceValue` will either cooperate with the garbage collection so that its information is updated after the garbage collection, or it will be invalidated implicitly before the garbage collection.</span></span>  
  
 <span data-ttu-id="03677-124">L' `ICorDebugReferenceValue` oggetto può essere invalidato in modo implicito dopo che è stato proseguito il processo sottoposto a debug.</span><span class="sxs-lookup"><span data-stu-id="03677-124">The `ICorDebugReferenceValue` object may be implicitly invalidated after the debugged process has been continued.</span></span> <span data-ttu-id="03677-125">Il "ICorDebugHandleValue" derivato non viene invalidato fino a quando non viene rilasciato o esposto in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="03677-125">The derived "ICorDebugHandleValue" is not invalidated until it is explicitly released or exposed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="03677-126">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="03677-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03677-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="03677-127">Requirements</span></span>  
 <span data-ttu-id="03677-128">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03677-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03677-129">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="03677-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03677-130">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03677-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03677-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03677-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03677-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03677-132">See also</span></span>

- [<span data-ttu-id="03677-133">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="03677-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

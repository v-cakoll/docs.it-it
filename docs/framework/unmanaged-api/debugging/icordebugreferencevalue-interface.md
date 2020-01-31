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
ms.openlocfilehash: 2efba22b4ec372c5ddedd4982a29d66945d3511c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792123"
---
# <a name="icordebugreferencevalue-interface"></a><span data-ttu-id="d15e0-102">Interfaccia ICorDebugReferenceValue</span><span class="sxs-lookup"><span data-stu-id="d15e0-102">ICorDebugReferenceValue Interface</span></span>
<span data-ttu-id="d15e0-103">Fornisce metodi che gestiscono un valore che è un riferimento a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="d15e0-103">Provides methods that manage a value that is a reference to an object.</span></span> <span data-ttu-id="d15e0-104">(Ovvero, questa interfaccia fornisce metodi per la gestione di un puntatore). Questa interfaccia implementa "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="d15e0-104">(That is, this interface provides methods that manage a pointer.) This interface implements "ICorDebugValue".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d15e0-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="d15e0-105">Methods</span></span>  
  
|<span data-ttu-id="d15e0-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="d15e0-106">Method</span></span>|<span data-ttu-id="d15e0-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d15e0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d15e0-108">Metodo Dereference</span><span class="sxs-lookup"><span data-stu-id="d15e0-108">Dereference Method</span></span>](icordebugreferencevalue-dereference-method.md)|<span data-ttu-id="d15e0-109">Ottiene l'oggetto a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="d15e0-109">Gets the object that is referenced.</span></span>|  
|[<span data-ttu-id="d15e0-110">Metodo DereferenceStrong</span><span class="sxs-lookup"><span data-stu-id="d15e0-110">DereferenceStrong Method</span></span>](icordebugreferencevalue-dereferencestrong-method.md)|<span data-ttu-id="d15e0-111">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="d15e0-111">Not implemented.</span></span> <span data-ttu-id="d15e0-112">Non chiamare questo metodo.</span><span class="sxs-lookup"><span data-stu-id="d15e0-112">Do not call this method.</span></span>|  
|[<span data-ttu-id="d15e0-113">Metodo GetValue</span><span class="sxs-lookup"><span data-stu-id="d15e0-113">GetValue Method</span></span>](icordebugreferencevalue-getvalue-method.md)|<span data-ttu-id="d15e0-114">Ottiene l'indirizzo di memoria corrente dell'oggetto a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="d15e0-114">Gets the current memory address of the referenced object.</span></span>|  
|[<span data-ttu-id="d15e0-115">Metodo IsNull</span><span class="sxs-lookup"><span data-stu-id="d15e0-115">IsNull Method</span></span>](icordebugreferencevalue-isnull-method.md)|<span data-ttu-id="d15e0-116">Ottiene un valore che indica se questo `ICorDebugReferenceValue` è un valore null, nel qual caso l'`ICorDebugReferenceValue` non punta a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="d15e0-116">Gets a value that indicates whether this `ICorDebugReferenceValue` is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>|  
|[<span data-ttu-id="d15e0-117">Metodo SetValue</span><span class="sxs-lookup"><span data-stu-id="d15e0-117">SetValue Method</span></span>](icordebugreferencevalue-setvalue-method.md)|<span data-ttu-id="d15e0-118">Imposta l'indirizzo di memoria corrente.</span><span class="sxs-lookup"><span data-stu-id="d15e0-118">Sets the current memory address.</span></span> <span data-ttu-id="d15e0-119">Questo metodo imposta questa `ICorDebugReferenceValue` in modo che punti a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="d15e0-119">That is, this method sets this `ICorDebugReferenceValue` to point to an object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d15e0-120">Note</span><span class="sxs-lookup"><span data-stu-id="d15e0-120">Remarks</span></span>  
 <span data-ttu-id="d15e0-121">Il Common Language Runtime (CLR) può eseguire una Garbage Collection sugli oggetti quando il processo sottoposto a debug viene continuato.</span><span class="sxs-lookup"><span data-stu-id="d15e0-121">The common language runtime (CLR) may do a garbage collection on objects when the debugged process is continued.</span></span> <span data-ttu-id="d15e0-122">Il Garbage Collection può spostare gli oggetti in memoria.</span><span class="sxs-lookup"><span data-stu-id="d15e0-122">The garbage collection may move objects around in memory.</span></span> <span data-ttu-id="d15e0-123">Un `ICorDebugReferenceValue` collaborerà con l'Garbage Collection in modo che le informazioni vengano aggiornate dopo l'Garbage Collection o verranno invalidate in modo implicito prima del Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="d15e0-123">An `ICorDebugReferenceValue` will either cooperate with the garbage collection so that its information is updated after the garbage collection, or it will be invalidated implicitly before the garbage collection.</span></span>  
  
 <span data-ttu-id="d15e0-124">L'oggetto `ICorDebugReferenceValue` può essere invalidato in modo implicito dopo che è stato proseguito il processo sottoposto a debug.</span><span class="sxs-lookup"><span data-stu-id="d15e0-124">The `ICorDebugReferenceValue` object may be implicitly invalidated after the debugged process has been continued.</span></span> <span data-ttu-id="d15e0-125">Il "ICorDebugHandleValue" derivato non viene invalidato fino a quando non viene rilasciato o esposto in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="d15e0-125">The derived "ICorDebugHandleValue" is not invalidated until it is explicitly released or exposed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d15e0-126">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="d15e0-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d15e0-127">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="d15e0-127">Requirements</span></span>  
 <span data-ttu-id="d15e0-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d15e0-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d15e0-129">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d15e0-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d15e0-130">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d15e0-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d15e0-131">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d15e0-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d15e0-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d15e0-132">See also</span></span>

- [<span data-ttu-id="d15e0-133">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="d15e0-133">Debugging Interfaces</span></span>](debugging-interfaces.md)

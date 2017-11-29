---
title: ICorDebugReferenceValue Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugReferenceValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugReferenceValue
helpviewer_keywords: ICorDebugReferenceValue interface [.NET Framework debugging]
ms.assetid: 2040e2be-119a-4cfb-ae52-b0b6f052665c
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d11cb4cbd6baa1e0d381c9fb11d5a3343287cf55
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugreferencevalue-interface1"></a><span data-ttu-id="0941b-102">ICorDebugReferenceValue Interface1</span><span class="sxs-lookup"><span data-stu-id="0941b-102">ICorDebugReferenceValue Interface1</span></span>
<span data-ttu-id="0941b-103">Fornisce metodi che gestiscono un valore che è un riferimento a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="0941b-103">Provides methods that manage a value that is a reference to an object.</span></span> <span data-ttu-id="0941b-104">(Ovvero, questa interfaccia fornisce metodi che gestiscono un puntatore) Questa interfaccia implementa "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="0941b-104">(That is, this interface provides methods that manage a pointer.) This interface implements "ICorDebugValue".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0941b-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="0941b-105">Methods</span></span>  
  
|<span data-ttu-id="0941b-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="0941b-106">Method</span></span>|<span data-ttu-id="0941b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0941b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0941b-108">Dereference (metodo)</span><span class="sxs-lookup"><span data-stu-id="0941b-108">Dereference Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereference-method.md)|<span data-ttu-id="0941b-109">Ottiene l'oggetto a cui fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="0941b-109">Gets the object that is referenced.</span></span>|  
|[<span data-ttu-id="0941b-110">DereferenceStrong (metodo)</span><span class="sxs-lookup"><span data-stu-id="0941b-110">DereferenceStrong Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereferencestrong-method.md)|<span data-ttu-id="0941b-111">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="0941b-111">Not implemented.</span></span> <span data-ttu-id="0941b-112">Non chiamare questo metodo.</span><span class="sxs-lookup"><span data-stu-id="0941b-112">Do not call this method.</span></span>|  
|[<span data-ttu-id="0941b-113">GetValue (metodo)</span><span class="sxs-lookup"><span data-stu-id="0941b-113">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-getvalue-method.md)|<span data-ttu-id="0941b-114">Ottiene l'indirizzo di memoria corrente dell'oggetto di riferimento.</span><span class="sxs-lookup"><span data-stu-id="0941b-114">Gets the current memory address of the referenced object.</span></span>|  
|[<span data-ttu-id="0941b-115">IsNull (metodo)</span><span class="sxs-lookup"><span data-stu-id="0941b-115">IsNull Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-isnull-method.md)|<span data-ttu-id="0941b-116">Ottiene un valore che indica se questo `ICorDebugReferenceValue` è un valore null, nel qual caso il `ICorDebugReferenceValue` non punta a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="0941b-116">Gets a value that indicates whether this `ICorDebugReferenceValue` is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>|  
|[<span data-ttu-id="0941b-117">SetValue (metodo)</span><span class="sxs-lookup"><span data-stu-id="0941b-117">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-setvalue-method.md)|<span data-ttu-id="0941b-118">Imposta l'indirizzo di memoria corrente.</span><span class="sxs-lookup"><span data-stu-id="0941b-118">Sets the current memory address.</span></span> <span data-ttu-id="0941b-119">Ovvero, questo metodo imposta `ICorDebugReferenceValue` in modo che punti a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="0941b-119">That is, this method sets this `ICorDebugReferenceValue` to point to an object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0941b-120">Note</span><span class="sxs-lookup"><span data-stu-id="0941b-120">Remarks</span></span>  
 <span data-ttu-id="0941b-121">Common language runtime (CLR) può eseguire un'operazione di garbage collection sugli oggetti quando si continua il processo sottoposto a debug.</span><span class="sxs-lookup"><span data-stu-id="0941b-121">The common language runtime (CLR) may do a garbage collection on objects when the debugged process is continued.</span></span> <span data-ttu-id="0941b-122">Operazione di garbage collection può spostarsi oggetti in memoria.</span><span class="sxs-lookup"><span data-stu-id="0941b-122">The garbage collection may move objects around in memory.</span></span> <span data-ttu-id="0941b-123">Un `ICorDebugReferenceValue` interagirà con l'operazione di garbage collection in modo che le relative informazioni viene aggiornate dopo l'operazione di garbage collection o verrà invalidato in modo implicito prima operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="0941b-123">An `ICorDebugReferenceValue` will either cooperate with the garbage collection so that its information is updated after the garbage collection, or it will be invalidated implicitly before the garbage collection.</span></span>  
  
 <span data-ttu-id="0941b-124">Il `ICorDebugReferenceValue` oggetto può essere invalidato in modo implicito dopo il processo sottoposto a debug.</span><span class="sxs-lookup"><span data-stu-id="0941b-124">The `ICorDebugReferenceValue` object may be implicitly invalidated after the debugged process has been continued.</span></span> <span data-ttu-id="0941b-125">"L'interfaccia ICorDebugHandleValue derivata" non viene invalidata fino a quando non viene rilasciata o esposta in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="0941b-125">The derived "ICorDebugHandleValue" is not invalidated until it is explicitly released or exposed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0941b-126">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="0941b-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0941b-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0941b-127">Requirements</span></span>  
 <span data-ttu-id="0941b-128">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0941b-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0941b-129">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="0941b-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0941b-130">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0941b-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0941b-131">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0941b-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0941b-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0941b-132">See Also</span></span>  
    
    
 [<span data-ttu-id="0941b-133">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="0941b-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

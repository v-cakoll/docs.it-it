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
ms.openlocfilehash: 4709d1b8126436d4400c788891960100915cd1bc
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56971437"
---
# <a name="icordebugreferencevalue-interface"></a><span data-ttu-id="82785-102">Interfaccia ICorDebugReferenceValue</span><span class="sxs-lookup"><span data-stu-id="82785-102">ICorDebugReferenceValue Interface</span></span>
<span data-ttu-id="82785-103">Fornisce metodi che gestiscono un valore che è un riferimento a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="82785-103">Provides methods that manage a value that is a reference to an object.</span></span> <span data-ttu-id="82785-104">(Vale a dire, questa interfaccia fornisce metodi che gestiscono un puntatore.) Questa interfaccia implementerà "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="82785-104">(That is, this interface provides methods that manage a pointer.) This interface implements "ICorDebugValue".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="82785-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="82785-105">Methods</span></span>  
  
|<span data-ttu-id="82785-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="82785-106">Method</span></span>|<span data-ttu-id="82785-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="82785-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="82785-108">Metodo Dereference</span><span class="sxs-lookup"><span data-stu-id="82785-108">Dereference Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereference-method.md)|<span data-ttu-id="82785-109">Ottiene l'oggetto a cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="82785-109">Gets the object that is referenced.</span></span>|  
|[<span data-ttu-id="82785-110">Metodo DereferenceStrong</span><span class="sxs-lookup"><span data-stu-id="82785-110">DereferenceStrong Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereferencestrong-method.md)|<span data-ttu-id="82785-111">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="82785-111">Not implemented.</span></span> <span data-ttu-id="82785-112">Non chiamare questo metodo.</span><span class="sxs-lookup"><span data-stu-id="82785-112">Do not call this method.</span></span>|  
|[<span data-ttu-id="82785-113">Metodo GetValue</span><span class="sxs-lookup"><span data-stu-id="82785-113">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-getvalue-method.md)|<span data-ttu-id="82785-114">Ottiene l'indirizzo di memoria corrente dell'oggetto di riferimento.</span><span class="sxs-lookup"><span data-stu-id="82785-114">Gets the current memory address of the referenced object.</span></span>|  
|[<span data-ttu-id="82785-115">Metodo IsNull</span><span class="sxs-lookup"><span data-stu-id="82785-115">IsNull Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-isnull-method.md)|<span data-ttu-id="82785-116">Ottiene un valore che indica se questo `ICorDebugReferenceValue` è un valore null, nel qual caso il `ICorDebugReferenceValue` non punta a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="82785-116">Gets a value that indicates whether this `ICorDebugReferenceValue` is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>|  
|[<span data-ttu-id="82785-117">Metodo SetValue</span><span class="sxs-lookup"><span data-stu-id="82785-117">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-setvalue-method.md)|<span data-ttu-id="82785-118">Imposta l'indirizzo di memoria corrente.</span><span class="sxs-lookup"><span data-stu-id="82785-118">Sets the current memory address.</span></span> <span data-ttu-id="82785-119">Vale a dire, questo metodo imposta `ICorDebugReferenceValue` in modo che punti a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="82785-119">That is, this method sets this `ICorDebugReferenceValue` to point to an object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82785-120">Note</span><span class="sxs-lookup"><span data-stu-id="82785-120">Remarks</span></span>  
 <span data-ttu-id="82785-121">Common language runtime (CLR) può effettuare un'operazione di garbage collection sugli oggetti quando continua il processo sottoposto a debug.</span><span class="sxs-lookup"><span data-stu-id="82785-121">The common language runtime (CLR) may do a garbage collection on objects when the debugged process is continued.</span></span> <span data-ttu-id="82785-122">La garbage collection potrebbe spostare gli oggetti in memoria.</span><span class="sxs-lookup"><span data-stu-id="82785-122">The garbage collection may move objects around in memory.</span></span> <span data-ttu-id="82785-123">Un `ICorDebugReferenceValue` interagirà con l'operazione di garbage collection in modo che le relative informazioni viene aggiornate dopo l'operazione di garbage collection o verrà invalidato in modo implicito prima dell'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="82785-123">An `ICorDebugReferenceValue` will either cooperate with the garbage collection so that its information is updated after the garbage collection, or it will be invalidated implicitly before the garbage collection.</span></span>  
  
 <span data-ttu-id="82785-124">Il `ICorDebugReferenceValue` oggetto può essere invalidato in modo implicito dopo il processo sottoposto a debug.</span><span class="sxs-lookup"><span data-stu-id="82785-124">The `ICorDebugReferenceValue` object may be implicitly invalidated after the debugged process has been continued.</span></span> <span data-ttu-id="82785-125">Fino a quando non viene rilasciata o esposti in modo esplicito, derivato "ICorDebugHandleValue" non viene invalidata.</span><span class="sxs-lookup"><span data-stu-id="82785-125">The derived "ICorDebugHandleValue" is not invalidated until it is explicitly released or exposed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82785-126">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="82785-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82785-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="82785-127">Requirements</span></span>  
 <span data-ttu-id="82785-128">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82785-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82785-129">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="82785-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="82785-130">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82785-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82785-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82785-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82785-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82785-132">See also</span></span>


- [<span data-ttu-id="82785-133">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="82785-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

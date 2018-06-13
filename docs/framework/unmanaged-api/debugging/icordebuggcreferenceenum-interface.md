---
title: Interfaccia ICorDebugGCReferenceEnum
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum
helpviewer_keywords:
- ICorDebugGCReferenceEnum interface [.NET Framework debugging]
ms.assetid: 5f3c91c9-c035-454f-96cc-011cab1ea06b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fa8c3160dc779b2475dec63be896af5283cf5346
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418165"
---
# <a name="icordebuggcreferenceenum-interface"></a><span data-ttu-id="93481-102">Interfaccia ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="93481-102">ICorDebugGCReferenceEnum Interface</span></span>
<span data-ttu-id="93481-103">Fornisce un enumeratore per gli oggetti che verranno sottoposti a operazioni di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="93481-103">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="93481-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="93481-104">Methods</span></span>  
  
|<span data-ttu-id="93481-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="93481-105">Method</span></span>|<span data-ttu-id="93481-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="93481-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="93481-107">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="93481-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md)|<span data-ttu-id="93481-108">Ottiene il numero specificato di [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) istanze che contengono informazioni sugli oggetti che verranno sottoposti a garbage collection.</span><span class="sxs-lookup"><span data-stu-id="93481-108">Gets the specified number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93481-109">Note</span><span class="sxs-lookup"><span data-stu-id="93481-109">Remarks</span></span>  
 <span data-ttu-id="93481-110">Il `ICorDebugGCReferenceEnum` interfaccia implementa l'interfaccia "ICorDebugEnum".</span><span class="sxs-lookup"><span data-stu-id="93481-110">The `ICorDebugGCReferenceEnum` interface implements the "ICorDebugEnum" interface.</span></span>  
  
 <span data-ttu-id="93481-111">Un `ICorDebugGCReferenceEnum` istanza viene popolata con [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) istanze chiamando il [icordebugprocess5:: Enumerategcreferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="93481-111">An `ICorDebugGCReferenceEnum` instance is populated with [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances by calling the [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) method.</span></span> <span data-ttu-id="93481-112">[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) oggetti possono essere enumerati chiamando il [ICorDebugGCReference::Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="93481-112">[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects can be enumerated by calling the [ICorDebugGCReference::Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="93481-113">Il [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) gli oggetti nella raccolta popolato da questo metodo rappresentano tre tipi di oggetti:</span><span class="sxs-lookup"><span data-stu-id="93481-113">The [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects in the collection populated by this method represent three kinds of objects:</span></span>  
  
-   <span data-ttu-id="93481-114">Oggetti da tutti gli stack gestiti.</span><span class="sxs-lookup"><span data-stu-id="93481-114">Objects from all managed stacks.</span></span> <span data-ttu-id="93481-115">Questo include i riferimenti in tempo reale nel codice gestito, nonché gli oggetti creati da common language runtime.</span><span class="sxs-lookup"><span data-stu-id="93481-115">This includes live references in managed code as well as objects created by the common language runtime.</span></span>  
  
-   <span data-ttu-id="93481-116">Oggetti dalla tabella di handle.</span><span class="sxs-lookup"><span data-stu-id="93481-116">Objects from the handle table.</span></span> <span data-ttu-id="93481-117">Sono inclusi riferimenti forti (`HNDTYPE_STRONG` e `HNDTYPE_REFCOUNT`) e le variabili statiche in un modulo.</span><span class="sxs-lookup"><span data-stu-id="93481-117">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
-   <span data-ttu-id="93481-118">Oggetti dalla coda del finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="93481-118">Objects from the finalizer queue.</span></span> <span data-ttu-id="93481-119">Coda del finalizzatore radici di oggetti fino a quando non è stato eseguito il finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="93481-119">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93481-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="93481-120">Requirements</span></span>  
 <span data-ttu-id="93481-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93481-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93481-122">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="93481-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="93481-123">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="93481-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93481-124">**Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93481-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93481-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93481-125">See Also</span></span>  
 [<span data-ttu-id="93481-126">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="93481-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

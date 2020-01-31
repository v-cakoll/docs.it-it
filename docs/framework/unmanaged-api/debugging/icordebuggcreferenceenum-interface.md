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
ms.openlocfilehash: f01c27376191c3a2dddf56dae4b26c8b5193c73e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788646"
---
# <a name="icordebuggcreferenceenum-interface"></a><span data-ttu-id="9755d-102">Interfaccia ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="9755d-102">ICorDebugGCReferenceEnum Interface</span></span>
<span data-ttu-id="9755d-103">Fornisce un enumeratore per gli oggetti che verranno sottoposti a operazioni di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="9755d-103">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9755d-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="9755d-104">Methods</span></span>  
  
|<span data-ttu-id="9755d-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="9755d-105">Method</span></span>|<span data-ttu-id="9755d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9755d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9755d-107">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="9755d-107">Next Method</span></span>](icordebuggcreferenceenum-next-method.md)|<span data-ttu-id="9755d-108">Ottiene il numero specificato di istanze di [COR_GC_REFERENCE](cor-gc-reference-structure.md) che contengono informazioni sugli oggetti che verranno sottoposti a Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="9755d-108">Gets the specified number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9755d-109">Note</span><span class="sxs-lookup"><span data-stu-id="9755d-109">Remarks</span></span>  
 <span data-ttu-id="9755d-110">L'interfaccia `ICorDebugGCReferenceEnum` implementa l'interfaccia "ICorDebugEnum".</span><span class="sxs-lookup"><span data-stu-id="9755d-110">The `ICorDebugGCReferenceEnum` interface implements the "ICorDebugEnum" interface.</span></span>  
  
 <span data-ttu-id="9755d-111">Un'istanza di `ICorDebugGCReferenceEnum` viene popolata con [COR_GC_REFERENCE](cor-gc-reference-structure.md) istanze chiamando il metodo [ICorDebugProcess5:: EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9755d-111">An `ICorDebugGCReferenceEnum` instance is populated with [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances by calling the [ICorDebugProcess5::EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md) method.</span></span> <span data-ttu-id="9755d-112">È possibile enumerare gli oggetti [COR_GC_REFERENCE](cor-gc-reference-structure.md) chiamando il metodo [ICorDebugGCReference:: Next](icordebuggcreferenceenum-next-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9755d-112">[COR_GC_REFERENCE](cor-gc-reference-structure.md) objects can be enumerated by calling the [ICorDebugGCReference::Next](icordebuggcreferenceenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="9755d-113">Gli oggetti [COR_GC_REFERENCE](cor-gc-reference-structure.md) nella raccolta popolata da questo metodo rappresentano tre tipi di oggetti:</span><span class="sxs-lookup"><span data-stu-id="9755d-113">The [COR_GC_REFERENCE](cor-gc-reference-structure.md) objects in the collection populated by this method represent three kinds of objects:</span></span>  
  
- <span data-ttu-id="9755d-114">Oggetti da tutti gli stack gestiti.</span><span class="sxs-lookup"><span data-stu-id="9755d-114">Objects from all managed stacks.</span></span> <span data-ttu-id="9755d-115">Sono inclusi i riferimenti Live nel codice gestito e gli oggetti creati dal Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="9755d-115">This includes live references in managed code as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="9755d-116">Oggetti dalla tabella di handle.</span><span class="sxs-lookup"><span data-stu-id="9755d-116">Objects from the handle table.</span></span> <span data-ttu-id="9755d-117">Sono inclusi i riferimenti sicuri (`HNDTYPE_STRONG` e `HNDTYPE_REFCOUNT`) e le variabili statiche in un modulo.</span><span class="sxs-lookup"><span data-stu-id="9755d-117">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="9755d-118">Oggetti dalla coda del finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="9755d-118">Objects from the finalizer queue.</span></span> <span data-ttu-id="9755d-119">Il finalizzatore Accoda oggetti radice fino all'esecuzione del finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="9755d-119">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9755d-120">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="9755d-120">Requirements</span></span>  
 <span data-ttu-id="9755d-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9755d-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9755d-122">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9755d-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9755d-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9755d-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9755d-124">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9755d-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9755d-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9755d-125">See also</span></span>

- [<span data-ttu-id="9755d-126">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="9755d-126">Debugging Interfaces</span></span>](debugging-interfaces.md)

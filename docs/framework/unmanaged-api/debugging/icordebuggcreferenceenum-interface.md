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
ms.openlocfilehash: 5650a7e6e6cb0108f0d043914ea94debe2b703bf
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213101"
---
# <a name="icordebuggcreferenceenum-interface"></a><span data-ttu-id="a819b-102">Interfaccia ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="a819b-102">ICorDebugGCReferenceEnum Interface</span></span>
<span data-ttu-id="a819b-103">Fornisce un enumeratore per gli oggetti che verranno sottoposti a operazioni di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a819b-103">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a819b-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="a819b-104">Methods</span></span>  
  
|<span data-ttu-id="a819b-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="a819b-105">Method</span></span>|<span data-ttu-id="a819b-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a819b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a819b-107">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="a819b-107">Next Method</span></span>](icordebuggcreferenceenum-next-method.md)|<span data-ttu-id="a819b-108">Ottiene il numero specificato di istanze di [COR_GC_REFERENCE](cor-gc-reference-structure.md) che contengono informazioni sugli oggetti che verranno sottoposti a Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a819b-108">Gets the specified number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a819b-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a819b-109">Remarks</span></span>  
 <span data-ttu-id="a819b-110">L' `ICorDebugGCReferenceEnum` interfaccia implementa l'interfaccia "ICorDebugEnum".</span><span class="sxs-lookup"><span data-stu-id="a819b-110">The `ICorDebugGCReferenceEnum` interface implements the "ICorDebugEnum" interface.</span></span>  
  
 <span data-ttu-id="a819b-111">Un' `ICorDebugGCReferenceEnum` istanza viene popolata con [COR_GC_REFERENCE](cor-gc-reference-structure.md) istanze chiamando il metodo [ICorDebugProcess5:: EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a819b-111">An `ICorDebugGCReferenceEnum` instance is populated with [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances by calling the [ICorDebugProcess5::EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md) method.</span></span> <span data-ttu-id="a819b-112">È possibile enumerare gli oggetti [COR_GC_REFERENCE](cor-gc-reference-structure.md) chiamando il metodo [ICorDebugGCReference:: Next](icordebuggcreferenceenum-next-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a819b-112">[COR_GC_REFERENCE](cor-gc-reference-structure.md) objects can be enumerated by calling the [ICorDebugGCReference::Next](icordebuggcreferenceenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="a819b-113">Gli oggetti [COR_GC_REFERENCE](cor-gc-reference-structure.md) nella raccolta popolata da questo metodo rappresentano tre tipi di oggetti:</span><span class="sxs-lookup"><span data-stu-id="a819b-113">The [COR_GC_REFERENCE](cor-gc-reference-structure.md) objects in the collection populated by this method represent three kinds of objects:</span></span>  
  
- <span data-ttu-id="a819b-114">Oggetti da tutti gli stack gestiti.</span><span class="sxs-lookup"><span data-stu-id="a819b-114">Objects from all managed stacks.</span></span> <span data-ttu-id="a819b-115">Sono inclusi i riferimenti Live nel codice gestito e gli oggetti creati dal Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="a819b-115">This includes live references in managed code as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="a819b-116">Oggetti dalla tabella di handle.</span><span class="sxs-lookup"><span data-stu-id="a819b-116">Objects from the handle table.</span></span> <span data-ttu-id="a819b-117">Sono inclusi i riferimenti sicuri ( `HNDTYPE_STRONG` e `HNDTYPE_REFCOUNT` ) e le variabili statiche in un modulo.</span><span class="sxs-lookup"><span data-stu-id="a819b-117">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="a819b-118">Oggetti dalla coda del finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="a819b-118">Objects from the finalizer queue.</span></span> <span data-ttu-id="a819b-119">Il finalizzatore Accoda oggetti radice fino all'esecuzione del finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="a819b-119">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a819b-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a819b-120">Requirements</span></span>  
 <span data-ttu-id="a819b-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a819b-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a819b-122">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a819b-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a819b-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a819b-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a819b-124">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a819b-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a819b-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a819b-125">See also</span></span>

- [<span data-ttu-id="a819b-126">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a819b-126">Debugging Interfaces</span></span>](debugging-interfaces.md)

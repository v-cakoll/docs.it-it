---
title: Metodo ICorDebugProcess5::EnumerateHandles
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHandles
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHandles
helpviewer_keywords:
- EnumerateHandles method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHandles method [.NET Framework debugging]
ms.assetid: 7d7fa796-0dc6-4ee8-9d56-40166246d91d
topic_type:
- apiref
ms.openlocfilehash: 2a1653055a3834ce1bed0e7de7877b255bea0c38
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792422"
---
# <a name="icordebugprocess5enumeratehandles-method"></a><span data-ttu-id="aa4d3-102">Metodo ICorDebugProcess5::EnumerateHandles</span><span class="sxs-lookup"><span data-stu-id="aa4d3-102">ICorDebugProcess5::EnumerateHandles Method</span></span>
<span data-ttu-id="aa4d3-103">Ottiene un enumeratore per gli handle di oggetto in un processo.</span><span class="sxs-lookup"><span data-stu-id="aa4d3-103">Gets an enumerator for object handles in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa4d3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aa4d3-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa4d3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="aa4d3-105">Parameters</span></span>  
 `types`  
 <span data-ttu-id="aa4d3-106">in Combinazione bit per bit di valori [CorGCReferenceType](corgcreferencetype-enumeration.md) che specifica il tipo di handle da includere nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="aa4d3-106">[in] A bitwise combination of [CorGCReferenceType](corgcreferencetype-enumeration.md) values that specifies the type of handles to include in the collection.</span></span>  
  
 `ppENum`  
 <span data-ttu-id="aa4d3-107">out Puntatore all'indirizzo di un [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) che rappresenta un enumeratore per gli oggetti di cui eseguire il Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="aa4d3-107">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa4d3-108">Note</span><span class="sxs-lookup"><span data-stu-id="aa4d3-108">Remarks</span></span>  
 <span data-ttu-id="aa4d3-109">`EnumerateHandles` è una funzione helper che supporta l'ispezione della tabella dell'handle.</span><span class="sxs-lookup"><span data-stu-id="aa4d3-109">`EnumerateHandles` is a helper function that supports inspection of the handle table.</span></span> <span data-ttu-id="aa4d3-110">È simile al metodo [ICorDebugProcess5:: EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md) , ad eccezione del fatto che anziché popolare una raccolta [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) con tutti gli oggetti da sottoporre a Garbage Collection, include solo gli oggetti che hanno handle dalla tabella di handle.</span><span class="sxs-lookup"><span data-stu-id="aa4d3-110">It is similar to the [ICorDebugProcess5::EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md) method, except that rather than populating an [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) collection with all objects to be garbage-collected, it includes only objects that have handles from the handle table.</span></span>  
  
 <span data-ttu-id="aa4d3-111">Il parametro `types` specifica i tipi di handle da includere nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="aa4d3-111">The `types` parameter specifies the handle types to include in the collection.</span></span> <span data-ttu-id="aa4d3-112">`types` può essere uno dei tre membri seguenti dell'enumerazione [CorGCReferenceType](corgcreferencetype-enumeration.md) :</span><span class="sxs-lookup"><span data-stu-id="aa4d3-112">`types` can be any of the following three members of the [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration:</span></span>  
  
- <span data-ttu-id="aa4d3-113">`CorHandleStrongOnly` (gestisce solo i riferimenti sicuri).</span><span class="sxs-lookup"><span data-stu-id="aa4d3-113">`CorHandleStrongOnly` (handles to strong references only).</span></span>  
  
- <span data-ttu-id="aa4d3-114">`CorHandleWeakOnly` (gestisce solo i riferimenti deboli).</span><span class="sxs-lookup"><span data-stu-id="aa4d3-114">`CorHandleWeakOnly` (handles to weak references only).</span></span>  
  
- <span data-ttu-id="aa4d3-115">`CorHandleAll` (tutti gli handle).</span><span class="sxs-lookup"><span data-stu-id="aa4d3-115">`CorHandleAll` (all handles).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa4d3-116">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="aa4d3-116">Requirements</span></span>  
 <span data-ttu-id="aa4d3-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa4d3-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa4d3-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aa4d3-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aa4d3-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa4d3-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa4d3-120">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa4d3-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa4d3-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa4d3-121">See also</span></span>

- [<span data-ttu-id="aa4d3-122">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="aa4d3-122">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="aa4d3-123">Debug</span><span class="sxs-lookup"><span data-stu-id="aa4d3-123">Debugging</span></span>](index.md)

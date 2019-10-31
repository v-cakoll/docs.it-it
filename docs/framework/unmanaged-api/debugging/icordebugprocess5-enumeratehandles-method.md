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
ms.openlocfilehash: e0e68dba1f4d9ac5fa618aa842b823dcc046e70e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129683"
---
# <a name="icordebugprocess5enumeratehandles-method"></a><span data-ttu-id="dfe0e-102">Metodo ICorDebugProcess5::EnumerateHandles</span><span class="sxs-lookup"><span data-stu-id="dfe0e-102">ICorDebugProcess5::EnumerateHandles Method</span></span>
<span data-ttu-id="dfe0e-103">Ottiene un enumeratore per gli handle di oggetto in un processo.</span><span class="sxs-lookup"><span data-stu-id="dfe0e-103">Gets an enumerator for object handles in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfe0e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dfe0e-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dfe0e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dfe0e-105">Parameters</span></span>  
 `types`  
 <span data-ttu-id="dfe0e-106">in Combinazione bit per bit di valori [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) che specifica il tipo di handle da includere nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="dfe0e-106">[in] A bitwise combination of [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) values that specifies the type of handles to include in the collection.</span></span>  
  
 `ppENum`  
 <span data-ttu-id="dfe0e-107">out Puntatore all'indirizzo di un [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) che rappresenta un enumeratore per gli oggetti di cui eseguire il Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="dfe0e-107">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dfe0e-108">Note</span><span class="sxs-lookup"><span data-stu-id="dfe0e-108">Remarks</span></span>  
 <span data-ttu-id="dfe0e-109">`EnumerateHandles` è una funzione helper che supporta l'ispezione della tabella dell'handle.</span><span class="sxs-lookup"><span data-stu-id="dfe0e-109">`EnumerateHandles` is a helper function that supports inspection of the handle table.</span></span> <span data-ttu-id="dfe0e-110">È simile al metodo [ICorDebugProcess5:: EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) , con la differenza che anziché popolare una raccolta [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) con tutti gli oggetti da sottoporre a Garbage Collection, include solo gli oggetti con handle da tabella dell'handle.</span><span class="sxs-lookup"><span data-stu-id="dfe0e-110">It is similar to the [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) method, except that rather than populating an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) collection with all objects to be garbage-collected, it includes only objects that have handles from the handle table.</span></span>  
  
 <span data-ttu-id="dfe0e-111">Il parametro `types` specifica i tipi di handle da includere nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="dfe0e-111">The `types` parameter specifies the handle types to include in the collection.</span></span> <span data-ttu-id="dfe0e-112">`types` può essere uno dei tre membri seguenti dell'enumerazione [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) :</span><span class="sxs-lookup"><span data-stu-id="dfe0e-112">`types` can be any of the following three members of the [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration:</span></span>  
  
- <span data-ttu-id="dfe0e-113">`CorHandleStrongOnly` (gestisce solo i riferimenti sicuri).</span><span class="sxs-lookup"><span data-stu-id="dfe0e-113">`CorHandleStrongOnly` (handles to strong references only).</span></span>  
  
- <span data-ttu-id="dfe0e-114">`CorHandleWeakOnly` (gestisce solo i riferimenti deboli).</span><span class="sxs-lookup"><span data-stu-id="dfe0e-114">`CorHandleWeakOnly` (handles to weak references only).</span></span>  
  
- <span data-ttu-id="dfe0e-115">`CorHandleAll` (tutti gli handle).</span><span class="sxs-lookup"><span data-stu-id="dfe0e-115">`CorHandleAll` (all handles).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfe0e-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dfe0e-116">Requirements</span></span>  
 <span data-ttu-id="dfe0e-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfe0e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfe0e-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dfe0e-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dfe0e-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dfe0e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dfe0e-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfe0e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfe0e-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dfe0e-121">See also</span></span>

- [<span data-ttu-id="dfe0e-122">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="dfe0e-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="dfe0e-123">Debug</span><span class="sxs-lookup"><span data-stu-id="dfe0e-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

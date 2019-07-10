---
title: Metodo ICorDebugProcess5::EnumerateGCReferences
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateGCReferences
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateGCReferences
helpviewer_keywords:
- EnumerateGCReferences method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateGCReferences method [.NET Framework debugging]
ms.assetid: 86c397c3-81d8-463e-a248-3cbe06c44d9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d70797d810d6dd2fe97c1f0f3b9c45a18fb2afba
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767550"
---
# <a name="icordebugprocess5enumerategcreferences-method"></a><span data-ttu-id="fbbb3-102">Metodo ICorDebugProcess5::EnumerateGCReferences</span><span class="sxs-lookup"><span data-stu-id="fbbb3-102">ICorDebugProcess5::EnumerateGCReferences Method</span></span>
<span data-ttu-id="fbbb3-103">Ottiene un enumeratore per tutti gli oggetti che devono essere sottoposto a garbage collection in un processo.</span><span class="sxs-lookup"><span data-stu-id="fbbb3-103">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbbb3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fbbb3-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,   
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fbbb3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fbbb3-105">Parameters</span></span>  
 `enumerateWeakReferences`  
 <span data-ttu-id="fbbb3-106">[in] Valore booleano che indica se i riferimenti deboli sono anche da enumerare.</span><span class="sxs-lookup"><span data-stu-id="fbbb3-106">[in] A Boolean value that indicates whether weak references are also to be enumerated.</span></span> <span data-ttu-id="fbbb3-107">Se `enumerateWeakReferences` viene `true`, il `ppEnum` enumeratore include riferimenti forti e i riferimenti deboli.</span><span class="sxs-lookup"><span data-stu-id="fbbb3-107">If `enumerateWeakReferences` is `true`, the `ppEnum` enumerator includes both strong references and weak references.</span></span> <span data-ttu-id="fbbb3-108">Se `enumerateWeakReferences` è `false`, l'enumeratore include solo i riferimenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="fbbb3-108">If `enumerateWeakReferences` is `false`, the enumerator includes only strong references.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="fbbb3-109">[out] Un puntatore all'indirizzo di un [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) vale a dire un enumeratore per gli oggetti per essere sottoposto a garbage collection.</span><span class="sxs-lookup"><span data-stu-id="fbbb3-109">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fbbb3-110">Note</span><span class="sxs-lookup"><span data-stu-id="fbbb3-110">Remarks</span></span>  
 <span data-ttu-id="fbbb3-111">Questo metodo fornisce un modo per determinare la catena di definizione radice completa per qualsiasi oggetto gestito in un processo e può essere utilizzato per determinare il motivo per cui un oggetto è ancora attivo.</span><span class="sxs-lookup"><span data-stu-id="fbbb3-111">This method provides a way to determine the full rooting chain for any managed object in a process and can be used to determine why an object is still alive.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbbb3-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fbbb3-112">Requirements</span></span>  
 <span data-ttu-id="fbbb3-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbbb3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbbb3-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fbbb3-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fbbb3-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fbbb3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fbbb3-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbbb3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbbb3-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fbbb3-117">See also</span></span>

- [<span data-ttu-id="fbbb3-118">Interfaccia ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="fbbb3-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="fbbb3-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="fbbb3-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

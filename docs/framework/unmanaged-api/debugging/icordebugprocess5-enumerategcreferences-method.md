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
ms.openlocfilehash: 84b5da043f9bd437ee9099135ba865c1ab23bb9d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129661"
---
# <a name="icordebugprocess5enumerategcreferences-method"></a><span data-ttu-id="e8e31-102">Metodo ICorDebugProcess5::EnumerateGCReferences</span><span class="sxs-lookup"><span data-stu-id="e8e31-102">ICorDebugProcess5::EnumerateGCReferences Method</span></span>
<span data-ttu-id="e8e31-103">Ottiene un enumeratore per tutti gli oggetti che devono essere sottoposti a Garbage Collection in un processo.</span><span class="sxs-lookup"><span data-stu-id="e8e31-103">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8e31-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8e31-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,   
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8e31-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e8e31-105">Parameters</span></span>  
 `enumerateWeakReferences`  
 <span data-ttu-id="e8e31-106">in Valore booleano che indica se devono essere enumerati anche i riferimenti deboli.</span><span class="sxs-lookup"><span data-stu-id="e8e31-106">[in] A Boolean value that indicates whether weak references are also to be enumerated.</span></span> <span data-ttu-id="e8e31-107">Se `enumerateWeakReferences` è `true`, l'enumeratore `ppEnum` include sia riferimenti sicuri che riferimenti deboli.</span><span class="sxs-lookup"><span data-stu-id="e8e31-107">If `enumerateWeakReferences` is `true`, the `ppEnum` enumerator includes both strong references and weak references.</span></span> <span data-ttu-id="e8e31-108">Se `enumerateWeakReferences` è `false`, l'enumeratore include solo riferimenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="e8e31-108">If `enumerateWeakReferences` is `false`, the enumerator includes only strong references.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="e8e31-109">out Puntatore all'indirizzo di un [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) che rappresenta un enumeratore per gli oggetti di cui eseguire il Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="e8e31-109">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8e31-110">Note</span><span class="sxs-lookup"><span data-stu-id="e8e31-110">Remarks</span></span>  
 <span data-ttu-id="e8e31-111">Questo metodo fornisce un modo per determinare la catena di radice completa per qualsiasi oggetto gestito in un processo e può essere utilizzato per determinare il motivo per cui un oggetto è ancora attivo.</span><span class="sxs-lookup"><span data-stu-id="e8e31-111">This method provides a way to determine the full rooting chain for any managed object in a process and can be used to determine why an object is still alive.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8e31-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e8e31-112">Requirements</span></span>  
 <span data-ttu-id="e8e31-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8e31-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8e31-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e8e31-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e8e31-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8e31-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8e31-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8e31-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8e31-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8e31-117">See also</span></span>

- [<span data-ttu-id="e8e31-118">Interfaccia ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="e8e31-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="e8e31-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e8e31-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

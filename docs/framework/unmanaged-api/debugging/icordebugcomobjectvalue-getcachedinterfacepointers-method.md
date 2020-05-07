---
title: Metodo ICorDebugComObjectValue::GetCachedInterfacePointers
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue::GetCachedInterfacePointers
api_location:
- mscordbi.dll
f1_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers
helpviewer_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers method [.NET Framework debugging]
- GetCachedInterfacePointers method, ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 08dbd558-bd39-4263-94c2-71e70687aaf0
topic_type:
- apiref
ms.openlocfilehash: fa22c17ed7d5bcd689f21d2d855d9be7a6a8e164
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892803"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a><span data-ttu-id="b0be2-102">Metodo ICorDebugComObjectValue::GetCachedInterfacePointers</span><span class="sxs-lookup"><span data-stu-id="b0be2-102">ICorDebugComObjectValue::GetCachedInterfacePointers Method</span></span>
<span data-ttu-id="b0be2-103">Ottiene i puntatori di interfaccia raw memorizzati nella cache nel Runtime Callable Wrapper (RCW) corrente.</span><span class="sxs-lookup"><span data-stu-id="b0be2-103">Gets the raw interface pointers cached on the current runtime callable wrapper (RCW).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0be2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b0be2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedInterfacePointers(  
    [in] BOOL bIInspectableOnly,  
    [in] ULONG32 celt,  
    [out] ULONG32 *pceltFetched,  
    [out, size_is(celt), length_is(*pceltFetched) CORDB_ADDRESS *ptrs);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0be2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b0be2-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="b0be2-106">in Valore che indica se il metodo restituirà solo Windows Runtime interfacce (`IInspectable` interfacce) o tutte le interfacce COM memorizzate nella cache dal Runtime Callable Wrapper (RCW).</span><span class="sxs-lookup"><span data-stu-id="b0be2-106">[in] A value that indicates whether the method will return only Windows Runtime interfaces (`IInspectable` interfaces) or all COM interfaces that are cached by the runtime callable wrapper (RCW).</span></span>  
  
 `celt`  
 <span data-ttu-id="b0be2-107">in Numero di oggetti di cui devono essere recuperati gli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="b0be2-107">[in] The number of objects whose addresses are to be retrieved.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="b0be2-108">out Puntatore al numero di `CORDB_ADDRESS` valori effettivamente restituiti in. `ptrs`</span><span class="sxs-lookup"><span data-stu-id="b0be2-108">[out] A pointer to the number of `CORDB_ADDRESS` values actually returned in `ptrs`.</span></span>  
  
 `ptrs`  
 <span data-ttu-id="b0be2-109">Puntatore all'indirizzo iniziale di una matrice di `CORDB_ADDRESS` valori che contengono gli indirizzi degli oggetti dell'interfaccia memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="b0be2-109">A pointer to the starting address of an array of `CORDB_ADDRESS` values that contain the addresses of cached interface objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0be2-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b0be2-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0be2-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b0be2-111">Requirements</span></span>  
 <span data-ttu-id="b0be2-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0be2-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0be2-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0be2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0be2-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0be2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0be2-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0be2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0be2-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0be2-116">See also</span></span>

- [<span data-ttu-id="b0be2-117">Interfaccia ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="b0be2-117">ICorDebugComObjectValue Interface</span></span>](icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="b0be2-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="b0be2-118">Debugging Interfaces</span></span>](debugging-interfaces.md)

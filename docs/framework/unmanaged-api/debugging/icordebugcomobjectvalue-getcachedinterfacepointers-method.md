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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ef6fb76ca25a1255393b66c52d82cb94df2b48b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411902"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a><span data-ttu-id="a1040-102">Metodo ICorDebugComObjectValue::GetCachedInterfacePointers</span><span class="sxs-lookup"><span data-stu-id="a1040-102">ICorDebugComObjectValue::GetCachedInterfacePointers Method</span></span>
<span data-ttu-id="a1040-103">Ottiene i puntatori a interfaccia raw memorizzati nella cache sul corrente runtime callable wrapper (RCW).</span><span class="sxs-lookup"><span data-stu-id="a1040-103">Gets the raw interface pointers cached on the current runtime callable wrapper (RCW).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1040-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a1040-104">Syntax</span></span>  
  
```  
HRESULT GetCachedInterfacePointers(  
    [in] BOOL bIInspectableOnly,  
    [in] ULONG32 celt,  
    [out] ULONG32 *pceltFetched,  
    [out, size_is(celt), length_is(*pceltFetched) CORDB_ADDRESS *ptrs);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a1040-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a1040-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="a1040-106">[in] Un valore che indica se il metodo restituirà solo [!INCLUDE[wrt](../../../../includes/wrt-md.md)] interfacce (`IInspectable` interfacce) o tutte le interfacce COM che vengono memorizzati nella cache dal runtime callable wrapper (RCW).</span><span class="sxs-lookup"><span data-stu-id="a1040-106">[in] A value that indicates whether the method will return only [!INCLUDE[wrt](../../../../includes/wrt-md.md)] interfaces (`IInspectable` interfaces) or all COM interfaces that are cached by the runtime callable wrapper (RCW).</span></span>  
  
 `celt`  
 <span data-ttu-id="a1040-107">[in] Il numero di oggetti i cui indirizzi devono essere recuperate.</span><span class="sxs-lookup"><span data-stu-id="a1040-107">[in] The number of objects whose addresses are to be retrieved.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="a1040-108">[out] Un puntatore al numero di `CORDB_ADDRESS` valori effettivamente restituiti nella `ptrs`.</span><span class="sxs-lookup"><span data-stu-id="a1040-108">[out] A pointer to the number of `CORDB_ADDRESS` values actually returned in `ptrs`.</span></span>  
  
 `ptrs`  
 <span data-ttu-id="a1040-109">Un puntatore all'indirizzo iniziale di una matrice di `CORDB_ADDRESS` valori che contengono gli indirizzi di cache oggetti dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a1040-109">A pointer to the starting address of an array of `CORDB_ADDRESS` values that contain the addresses of cached interface objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1040-110">Note</span><span class="sxs-lookup"><span data-stu-id="a1040-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1040-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a1040-111">Requirements</span></span>  
 <span data-ttu-id="a1040-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1040-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1040-113">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="a1040-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1040-114">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="a1040-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1040-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1040-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1040-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1040-116">See Also</span></span>  
 [<span data-ttu-id="a1040-117">Interfaccia ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="a1040-117">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)  
 [<span data-ttu-id="a1040-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a1040-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

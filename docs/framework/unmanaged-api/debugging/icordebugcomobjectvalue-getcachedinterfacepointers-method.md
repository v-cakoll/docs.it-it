---
title: Metodo ICorDebugComObjectValue::GetCachedInterfacePointers
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugComObjectValue::GetCachedInterfacePointers
api_location: mscordbi.dll
f1_keywords: ICorDebugComObjectValue::GetCachedInterfacePointers
helpviewer_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers method [.NET Framework debugging]
- GetCachedInterfacePointers method, ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 08dbd558-bd39-4263-94c2-71e70687aaf0
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2b47395235ce21c7d40e4413702e6c655493a739
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a><span data-ttu-id="59dfc-102">Metodo ICorDebugComObjectValue::GetCachedInterfacePointers</span><span class="sxs-lookup"><span data-stu-id="59dfc-102">ICorDebugComObjectValue::GetCachedInterfacePointers Method</span></span>
<span data-ttu-id="59dfc-103">Ottiene i puntatori a interfaccia raw memorizzati nella cache sul corrente runtime callable wrapper (RCW).</span><span class="sxs-lookup"><span data-stu-id="59dfc-103">Gets the raw interface pointers cached on the current runtime callable wrapper (RCW).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59dfc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="59dfc-104">Syntax</span></span>  
  
```  
HRESULT GetCachedInterfacePointers(  
    [in] BOOL bIInspectableOnly,  
    [in] ULONG32 celt,  
    [out] ULONG32 *pceltFetched,  
    [out, size_is(celt), length_is(*pceltFetched) CORDB_ADDRESS *ptrs);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="59dfc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="59dfc-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="59dfc-106">[in] Un valore che indica se il metodo restituirà solo [!INCLUDE[wrt](../../../../includes/wrt-md.md)] interfacce (`IInspectable` interfacce) o tutte le interfacce COM che vengono memorizzati nella cache dal runtime callable wrapper (RCW).</span><span class="sxs-lookup"><span data-stu-id="59dfc-106">[in] A value that indicates whether the method will return only [!INCLUDE[wrt](../../../../includes/wrt-md.md)] interfaces (`IInspectable` interfaces) or all COM interfaces that are cached by the runtime callable wrapper (RCW).</span></span>  
  
 `celt`  
 <span data-ttu-id="59dfc-107">[in] Il numero di oggetti i cui indirizzi devono essere recuperate.</span><span class="sxs-lookup"><span data-stu-id="59dfc-107">[in] The number of objects whose addresses are to be retrieved.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="59dfc-108">[out] Un puntatore al numero di `CORDB_ADDRESS` valori effettivamente restituiti nella `ptrs`.</span><span class="sxs-lookup"><span data-stu-id="59dfc-108">[out] A pointer to the number of `CORDB_ADDRESS` values actually returned in `ptrs`.</span></span>  
  
 `ptrs`  
 <span data-ttu-id="59dfc-109">Un puntatore all'indirizzo iniziale di una matrice di `CORDB_ADDRESS` valori che contengono gli indirizzi di cache oggetti dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="59dfc-109">A pointer to the starting address of an array of `CORDB_ADDRESS` values that contain the addresses of cached interface objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59dfc-110">Note</span><span class="sxs-lookup"><span data-stu-id="59dfc-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59dfc-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="59dfc-111">Requirements</span></span>  
 <span data-ttu-id="59dfc-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59dfc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59dfc-113">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="59dfc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="59dfc-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59dfc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59dfc-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59dfc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59dfc-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59dfc-116">See Also</span></span>  
 [<span data-ttu-id="59dfc-117">Interfaccia ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="59dfc-117">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)  
 [<span data-ttu-id="59dfc-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="59dfc-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

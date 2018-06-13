---
title: Metodo ICorDebugTypeEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugTypeEnum::Next
helpviewer_keywords:
- ICorDebugTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugTypeEnum interface [.NET Framework debugging]
ms.assetid: d0fdeba3-c195-4ece-8caf-79b1f40025d2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9812fa4248533ccb898c98082e42e288c091f776
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420586"
---
# <a name="icordebugtypeenumnext-method"></a><span data-ttu-id="212d3-102">Metodo ICorDebugTypeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="212d3-102">ICorDebugTypeEnum::Next Method</span></span>
<span data-ttu-id="212d3-103">Ottiene il numero di istanze di "ICorDebugType" specificate da `celt` nell'enumerazione, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="212d3-103">Gets the number of "ICorDebugType" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="212d3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="212d3-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugType *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="212d3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="212d3-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="212d3-106">[in] Il numero di `ICorDebugType` istanze da recuperare.</span><span class="sxs-lookup"><span data-stu-id="212d3-106">[in] The number of `ICorDebugType` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="212d3-107">[out] Matrice di puntatori, ognuno dei quali punta a un `ICorDebugType` oggetto.</span><span class="sxs-lookup"><span data-stu-id="212d3-107">[out] An array of pointers, each of which points to an `ICorDebugType` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="212d3-108">[out] Puntatore al numero di `ICorDebugType` istanze effettivamente restituite.</span><span class="sxs-lookup"><span data-stu-id="212d3-108">[out] Pointer to the number of `ICorDebugType` instances actually returned.</span></span> <span data-ttu-id="212d3-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="212d3-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="212d3-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="212d3-110">Requirements</span></span>  
 <span data-ttu-id="212d3-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="212d3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="212d3-112">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="212d3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="212d3-113">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="212d3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="212d3-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="212d3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="212d3-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="212d3-115">See Also</span></span>  
 

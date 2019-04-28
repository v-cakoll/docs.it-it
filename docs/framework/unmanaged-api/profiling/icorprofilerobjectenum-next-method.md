---
title: Metodo ICorProfilerObjectEnum::Next
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Next
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Next
helpviewer_keywords:
- Next method, ICorProfilerObjectEnum interface [.NET Framework profiling]
- ICorProfilerObjectEnum::Next method [.NET Framework profiling]
ms.assetid: b420433c-5ebe-4986-bba1-97902e6db819
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 221752b537cd3a890ad646290a64a7022692f625
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597258"
---
# <a name="icorprofilerobjectenumnext-method"></a><span data-ttu-id="51187-102">Metodo ICorProfilerObjectEnum::Next</span><span class="sxs-lookup"><span data-stu-id="51187-102">ICorProfilerObjectEnum::Next Method</span></span>
<span data-ttu-id="51187-103">Ottiene il numero specificato di oggetti contigui da una raccolta sequenziale di oggetti, a partire dalla posizione corrente dell'enumeratore nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="51187-103">Gets the specified number of contiguous objects from a sequential collection of objects, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51187-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="51187-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG                    celt,  
    [out, size_is(celt), length_is(*pceltFetched)]    
        ObjectID                  objects[],  
    [out] ULONG                   *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51187-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="51187-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="51187-106">[in] Numero di oggetti da recuperare.</span><span class="sxs-lookup"><span data-stu-id="51187-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="51187-107">[out] Matrice di `ObjectID` valori, ognuno dei quali rappresenta un oggetto recuperato.</span><span class="sxs-lookup"><span data-stu-id="51187-107">[out] An array of `ObjectID` values, each of which represents a retrieved object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="51187-108">[out] Puntatore al numero di elementi effettivamente restituiti nella matrice `objects`.</span><span class="sxs-lookup"><span data-stu-id="51187-108">[out] A pointer to the number of elements actually returned in the `objects` array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51187-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="51187-109">Requirements</span></span>  
 <span data-ttu-id="51187-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51187-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51187-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="51187-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="51187-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51187-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51187-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51187-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51187-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51187-114">See also</span></span>

- [<span data-ttu-id="51187-115">Interfaccia ICorProfilerObjectEnum</span><span class="sxs-lookup"><span data-stu-id="51187-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)

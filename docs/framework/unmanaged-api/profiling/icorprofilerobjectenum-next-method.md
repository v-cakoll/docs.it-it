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
ms.openlocfilehash: 0c833416cca965f2655266152c5bdf5f11624d14
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861138"
---
# <a name="icorprofilerobjectenumnext-method"></a><span data-ttu-id="12430-102">Metodo ICorProfilerObjectEnum::Next</span><span class="sxs-lookup"><span data-stu-id="12430-102">ICorProfilerObjectEnum::Next Method</span></span>
<span data-ttu-id="12430-103">Ottiene il numero specificato di oggetti contigui da una raccolta sequenziale di oggetti, a partire dalla posizione corrente dell'enumeratore nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="12430-103">Gets the specified number of contiguous objects from a sequential collection of objects, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12430-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="12430-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG                    celt,  
    [out, size_is(celt), length_is(*pceltFetched)]    
        ObjectID                  objects[],  
    [out] ULONG                   *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12430-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="12430-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="12430-106">[in] Numero di oggetti da recuperare.</span><span class="sxs-lookup"><span data-stu-id="12430-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="12430-107">out Matrice di valori di `ObjectID`, ognuno dei quali rappresenta un oggetto recuperato.</span><span class="sxs-lookup"><span data-stu-id="12430-107">[out] An array of `ObjectID` values, each of which represents a retrieved object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="12430-108">[out] Puntatore al numero di elementi effettivamente restituiti nella matrice `objects`.</span><span class="sxs-lookup"><span data-stu-id="12430-108">[out] A pointer to the number of elements actually returned in the `objects` array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12430-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="12430-109">Requirements</span></span>  
 <span data-ttu-id="12430-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12430-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12430-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="12430-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="12430-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12430-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12430-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12430-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12430-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12430-114">See also</span></span>

- [<span data-ttu-id="12430-115">Interfaccia ICorProfilerObjectEnum</span><span class="sxs-lookup"><span data-stu-id="12430-115">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)

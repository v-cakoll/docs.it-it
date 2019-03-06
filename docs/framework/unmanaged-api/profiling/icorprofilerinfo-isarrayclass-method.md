---
title: Metodo ICorProfilerInfo::IsArrayClass
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.IsArrayClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::IsArrayClass
helpviewer_keywords:
- IsArrayClass method [.NET Framework profiling]
- ICorProfilerInfo::IsArrayClass method [.NET Framework profiling]
ms.assetid: 7f230961-23a6-4d56-ad2d-7a876d65705f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bf8e74094b15163fe86e18c397f4637557df8329
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468234"
---
# <a name="icorprofilerinfoisarrayclass-method"></a><span data-ttu-id="a875d-102">Metodo ICorProfilerInfo::IsArrayClass</span><span class="sxs-lookup"><span data-stu-id="a875d-102">ICorProfilerInfo::IsArrayClass Method</span></span>
<span data-ttu-id="a875d-103">Determina se la classe specificata è una classe di matrici.</span><span class="sxs-lookup"><span data-stu-id="a875d-103">Determines whether the specified class is an array class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a875d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a875d-104">Syntax</span></span>  
  
```  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a875d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a875d-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="a875d-106">[in] L'ID della classe da esaminare.</span><span class="sxs-lookup"><span data-stu-id="a875d-106">[in] The ID of the class to be examined.</span></span>  
  
 `pBaseElemType`  
 <span data-ttu-id="a875d-107">[out] Puntatore a un valore dell'enumerazione CorElementType che indica il tipo degli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="a875d-107">[out] A pointer to a value of the CorElementType enumeration that indicates the type of the array elements.</span></span>  
  
 `pBaseClassId`  
 <span data-ttu-id="a875d-108">[out] Un puntatore all'ID di classe degli elementi della matrice, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="a875d-108">[out] A pointer to the class ID of the array elements, when available.</span></span>  
  
 `pcRank`  
 <span data-ttu-id="a875d-109">[out] Puntatore a un intero che indica il numero di dimensioni (vale a dire, numero di dimensioni) della matrice.</span><span class="sxs-lookup"><span data-stu-id="a875d-109">[out] A pointer to an integer that indicates the rank (that is, number of dimensions) of the array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a875d-110">Note</span><span class="sxs-lookup"><span data-stu-id="a875d-110">Remarks</span></span>  
 <span data-ttu-id="a875d-111">Se la classe specificata è una classe di matrici, il `IsArrayClass` metodo viene restituito un HRESULT S_OK e i valori per parametri di output diverso da null.</span><span class="sxs-lookup"><span data-stu-id="a875d-111">If the specified class is an array class, the `IsArrayClass` method returns an S_OK HRESULT and values for any non-null output parameters.</span></span> <span data-ttu-id="a875d-112">In caso contrario, restituisce S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="a875d-112">Otherwise, it returns S_FALSE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a875d-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a875d-113">Requirements</span></span>  
 <span data-ttu-id="a875d-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a875d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a875d-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a875d-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a875d-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a875d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a875d-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a875d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a875d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a875d-118">See also</span></span>
- [<span data-ttu-id="a875d-119">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="a875d-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)

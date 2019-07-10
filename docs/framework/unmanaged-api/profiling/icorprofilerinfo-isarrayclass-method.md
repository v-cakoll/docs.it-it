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
ms.openlocfilehash: 5e00e7f39bc2f8c14db0676102a52089c7710bd6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772259"
---
# <a name="icorprofilerinfoisarrayclass-method"></a><span data-ttu-id="5fc51-102">Metodo ICorProfilerInfo::IsArrayClass</span><span class="sxs-lookup"><span data-stu-id="5fc51-102">ICorProfilerInfo::IsArrayClass Method</span></span>
<span data-ttu-id="5fc51-103">Determina se la classe specificata è una classe di matrici.</span><span class="sxs-lookup"><span data-stu-id="5fc51-103">Determines whether the specified class is an array class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fc51-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5fc51-104">Syntax</span></span>  
  
```cpp  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5fc51-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5fc51-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="5fc51-106">[in] L'ID della classe da esaminare.</span><span class="sxs-lookup"><span data-stu-id="5fc51-106">[in] The ID of the class to be examined.</span></span>  
  
 `pBaseElemType`  
 <span data-ttu-id="5fc51-107">[out] Puntatore a un valore dell'enumerazione CorElementType che indica il tipo degli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="5fc51-107">[out] A pointer to a value of the CorElementType enumeration that indicates the type of the array elements.</span></span>  
  
 `pBaseClassId`  
 <span data-ttu-id="5fc51-108">[out] Un puntatore all'ID di classe degli elementi della matrice, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="5fc51-108">[out] A pointer to the class ID of the array elements, when available.</span></span>  
  
 `pcRank`  
 <span data-ttu-id="5fc51-109">[out] Puntatore a un intero che indica il numero di dimensioni (vale a dire, numero di dimensioni) della matrice.</span><span class="sxs-lookup"><span data-stu-id="5fc51-109">[out] A pointer to an integer that indicates the rank (that is, number of dimensions) of the array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5fc51-110">Note</span><span class="sxs-lookup"><span data-stu-id="5fc51-110">Remarks</span></span>  
 <span data-ttu-id="5fc51-111">Se la classe specificata è una classe di matrici, il `IsArrayClass` metodo viene restituito un HRESULT S_OK e i valori per parametri di output diverso da null.</span><span class="sxs-lookup"><span data-stu-id="5fc51-111">If the specified class is an array class, the `IsArrayClass` method returns an S_OK HRESULT and values for any non-null output parameters.</span></span> <span data-ttu-id="5fc51-112">In caso contrario, restituisce S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="5fc51-112">Otherwise, it returns S_FALSE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fc51-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5fc51-113">Requirements</span></span>  
 <span data-ttu-id="5fc51-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fc51-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fc51-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5fc51-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5fc51-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5fc51-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5fc51-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fc51-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fc51-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5fc51-118">See also</span></span>

- [<span data-ttu-id="5fc51-119">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="5fc51-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)

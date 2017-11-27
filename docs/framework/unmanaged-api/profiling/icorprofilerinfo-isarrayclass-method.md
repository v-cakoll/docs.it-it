---
title: Metodo ICorProfilerInfo::IsArrayClass
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.IsArrayClass
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::IsArrayClass
helpviewer_keywords:
- IsArrayClass method [.NET Framework profiling]
- ICorProfilerInfo::IsArrayClass method [.NET Framework profiling]
ms.assetid: 7f230961-23a6-4d56-ad2d-7a876d65705f
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: cd07541095158d17b80333b83015d6b1f33a5dcc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfoisarrayclass-method"></a><span data-ttu-id="247c3-102">Metodo ICorProfilerInfo::IsArrayClass</span><span class="sxs-lookup"><span data-stu-id="247c3-102">ICorProfilerInfo::IsArrayClass Method</span></span>
<span data-ttu-id="247c3-103">Determina se la classe specificata è una classe della matrice.</span><span class="sxs-lookup"><span data-stu-id="247c3-103">Determines whether the specified class is an array class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="247c3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="247c3-104">Syntax</span></span>  
  
```  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="247c3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="247c3-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="247c3-106">[in] L'ID della classe da esaminare.</span><span class="sxs-lookup"><span data-stu-id="247c3-106">[in] The ID of the class to be examined.</span></span>  
  
 `pBaseElemType`  
 <span data-ttu-id="247c3-107">[out] Un puntatore a un valore dell'enumerazione CorElementType che indica il tipo degli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="247c3-107">[out] A pointer to a value of the CorElementType enumeration that indicates the type of the array elements.</span></span>  
  
 `pBaseClassId`  
 <span data-ttu-id="247c3-108">[out] Un puntatore all'ID classe degli elementi della matrice, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="247c3-108">[out] A pointer to the class ID of the array elements, when available.</span></span>  
  
 `pcRank`  
 <span data-ttu-id="247c3-109">[out] Un puntatore a un intero che indica il rango (numero di dimensioni) della matrice.</span><span class="sxs-lookup"><span data-stu-id="247c3-109">[out] A pointer to an integer that indicates the rank (that is, number of dimensions) of the array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="247c3-110">Note</span><span class="sxs-lookup"><span data-stu-id="247c3-110">Remarks</span></span>  
 <span data-ttu-id="247c3-111">Se la classe specificata è una classe della matrice, il `IsArrayClass` metodo restituisce un HRESULT S_OK e i valori per i parametri di output non null.</span><span class="sxs-lookup"><span data-stu-id="247c3-111">If the specified class is an array class, the `IsArrayClass` method returns an S_OK HRESULT and values for any non-null output parameters.</span></span> <span data-ttu-id="247c3-112">In caso contrario, restituisce S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="247c3-112">Otherwise, it returns S_FALSE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="247c3-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="247c3-113">Requirements</span></span>  
 <span data-ttu-id="247c3-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="247c3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="247c3-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="247c3-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="247c3-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="247c3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="247c3-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="247c3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="247c3-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="247c3-118">See Also</span></span>  
 [<span data-ttu-id="247c3-119">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="247c3-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)

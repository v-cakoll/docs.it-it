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
ms.openlocfilehash: a6e483d820d183afc8ba6a68fc4635730ffd1e51
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76869338"
---
# <a name="icorprofilerinfoisarrayclass-method"></a><span data-ttu-id="e83ca-102">Metodo ICorProfilerInfo::IsArrayClass</span><span class="sxs-lookup"><span data-stu-id="e83ca-102">ICorProfilerInfo::IsArrayClass Method</span></span>
<span data-ttu-id="e83ca-103">Determina se la classe specificata è una classe di matrici.</span><span class="sxs-lookup"><span data-stu-id="e83ca-103">Determines whether the specified class is an array class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e83ca-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e83ca-104">Syntax</span></span>  
  
```cpp  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e83ca-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e83ca-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="e83ca-106">in ID della classe da esaminare.</span><span class="sxs-lookup"><span data-stu-id="e83ca-106">[in] The ID of the class to be examined.</span></span>  
  
 `pBaseElemType`  
 <span data-ttu-id="e83ca-107">out Puntatore a un valore dell'enumerazione CorElementType che indica il tipo degli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="e83ca-107">[out] A pointer to a value of the CorElementType enumeration that indicates the type of the array elements.</span></span>  
  
 `pBaseClassId`  
 <span data-ttu-id="e83ca-108">out Puntatore all'ID della classe degli elementi della matrice, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="e83ca-108">[out] A pointer to the class ID of the array elements, when available.</span></span>  
  
 `pcRank`  
 <span data-ttu-id="e83ca-109">out Puntatore a un intero che indica il rango, ovvero il numero di dimensioni, della matrice.</span><span class="sxs-lookup"><span data-stu-id="e83ca-109">[out] A pointer to an integer that indicates the rank (that is, number of dimensions) of the array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e83ca-110">Note</span><span class="sxs-lookup"><span data-stu-id="e83ca-110">Remarks</span></span>  
 <span data-ttu-id="e83ca-111">Se la classe specificata è una classe di matrici, il metodo `IsArrayClass` restituisce un S_OK HRESULT e i valori per tutti i parametri di output non null.</span><span class="sxs-lookup"><span data-stu-id="e83ca-111">If the specified class is an array class, the `IsArrayClass` method returns an S_OK HRESULT and values for any non-null output parameters.</span></span> <span data-ttu-id="e83ca-112">In caso contrario, restituisce S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="e83ca-112">Otherwise, it returns S_FALSE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e83ca-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="e83ca-113">Requirements</span></span>  
 <span data-ttu-id="e83ca-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e83ca-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e83ca-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e83ca-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e83ca-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e83ca-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e83ca-117">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e83ca-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e83ca-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e83ca-118">See also</span></span>

- [<span data-ttu-id="e83ca-119">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="e83ca-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)

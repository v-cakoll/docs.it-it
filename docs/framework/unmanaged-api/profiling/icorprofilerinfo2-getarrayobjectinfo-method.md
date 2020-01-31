---
title: Metodo ICorProfilerInfo2::GetArrayObjectInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetArrayObjectInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetArrayObjectInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetArrayObjectInfo method [.NET Framework profiling]
- GetArrayObjectInfo method [.NET Framework profiling]
ms.assetid: bda75017-739f-4ce5-9000-f3b526e8473c
topic_type:
- apiref
ms.openlocfilehash: 839cd574e5352b74b47cd6242d5706bc6405d439
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862919"
---
# <a name="icorprofilerinfo2getarrayobjectinfo-method"></a><span data-ttu-id="442e5-102">Metodo ICorProfilerInfo2::GetArrayObjectInfo</span><span class="sxs-lookup"><span data-stu-id="442e5-102">ICorProfilerInfo2::GetArrayObjectInfo Method</span></span>
<span data-ttu-id="442e5-103">Ottiene informazioni dettagliate su un oggetto Array.</span><span class="sxs-lookup"><span data-stu-id="442e5-103">Gets detailed information about an array object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="442e5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="442e5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetArrayObjectInfo(  
    [in] ObjectID objectId,  
    [in] ULONG32 cDimensions,  
    [out, size_is(cDimensions), length_is(cDimensions)] ULONG32 pDimensionSizes[],  
    [out, size_is(cDimensions), length_is(cDimensions)] int pDimensionLowerBounds[],  
    [out] BYTE **ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="442e5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="442e5-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="442e5-106">in ID di un oggetto matrice valido.</span><span class="sxs-lookup"><span data-stu-id="442e5-106">[in] The ID of a valid array object.</span></span>  
  
 `cDimensions`  
 <span data-ttu-id="442e5-107">in Rango (numero di dimensioni) della matrice.</span><span class="sxs-lookup"><span data-stu-id="442e5-107">[in] The rank (number of dimensions) of the array.</span></span>  
  
 `pDimensionSizes`  
 <span data-ttu-id="442e5-108">out Matrice contenente Integer, ognuno dei quali rappresenta la dimensione di una dimensione della matrice.</span><span class="sxs-lookup"><span data-stu-id="442e5-108">[out] An array that contains integers, each representing the size of a dimension of the array.</span></span>  
  
 `pDimensionLowerBounds`  
 <span data-ttu-id="442e5-109">out Matrice contenente Integer, ognuno dei quali rappresenta il limite inferiore di una dimensione della matrice.</span><span class="sxs-lookup"><span data-stu-id="442e5-109">[out] An array that contains integers, each representing the lower bound of a dimension of the array.</span></span>  
  
 `ppData`  
 <span data-ttu-id="442e5-110">out Puntatore all'indirizzo del buffer non elaborato per la matrice, disposto in base alla C++ convenzione.</span><span class="sxs-lookup"><span data-stu-id="442e5-110">[out] A pointer to the address of the raw buffer for the array, which is laid out according to the C++ convention.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="442e5-111">Note</span><span class="sxs-lookup"><span data-stu-id="442e5-111">Remarks</span></span>  
 <span data-ttu-id="442e5-112">I `pDimensionSizes` e `pDimensionLowerBounds` sono matrici parallele, pertanto gli elementi che si trovano nello stesso indice in ogni matrice sono caratteristiche della stessa entità.</span><span class="sxs-lookup"><span data-stu-id="442e5-112">The `pDimensionSizes` and `pDimensionLowerBounds` are parallel arrays, so the elements located at the same index in each array are characteristics of the same entity.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="442e5-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="442e5-113">Requirements</span></span>  
 <span data-ttu-id="442e5-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="442e5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="442e5-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="442e5-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="442e5-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="442e5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="442e5-117">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="442e5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="442e5-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="442e5-118">See also</span></span>

- [<span data-ttu-id="442e5-119">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="442e5-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="442e5-120">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="442e5-120">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)

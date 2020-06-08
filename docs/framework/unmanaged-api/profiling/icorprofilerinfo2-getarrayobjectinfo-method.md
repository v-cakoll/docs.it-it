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
ms.openlocfilehash: 368b8f270797beb525e0745a29990667913f4071
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497356"
---
# <a name="icorprofilerinfo2getarrayobjectinfo-method"></a><span data-ttu-id="e9269-102">Metodo ICorProfilerInfo2::GetArrayObjectInfo</span><span class="sxs-lookup"><span data-stu-id="e9269-102">ICorProfilerInfo2::GetArrayObjectInfo Method</span></span>
<span data-ttu-id="e9269-103">Ottiene informazioni dettagliate su un oggetto Array.</span><span class="sxs-lookup"><span data-stu-id="e9269-103">Gets detailed information about an array object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9269-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e9269-104">Syntax</span></span>  
  
```cpp  
HRESULT GetArrayObjectInfo(  
    [in] ObjectID objectId,  
    [in] ULONG32 cDimensions,  
    [out, size_is(cDimensions), length_is(cDimensions)] ULONG32 pDimensionSizes[],  
    [out, size_is(cDimensions), length_is(cDimensions)] int pDimensionLowerBounds[],  
    [out] BYTE **ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9269-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e9269-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="e9269-106">in ID di un oggetto matrice valido.</span><span class="sxs-lookup"><span data-stu-id="e9269-106">[in] The ID of a valid array object.</span></span>  
  
 `cDimensions`  
 <span data-ttu-id="e9269-107">in Rango (numero di dimensioni) della matrice.</span><span class="sxs-lookup"><span data-stu-id="e9269-107">[in] The rank (number of dimensions) of the array.</span></span>  
  
 `pDimensionSizes`  
 <span data-ttu-id="e9269-108">out Matrice contenente Integer, ognuno dei quali rappresenta la dimensione di una dimensione della matrice.</span><span class="sxs-lookup"><span data-stu-id="e9269-108">[out] An array that contains integers, each representing the size of a dimension of the array.</span></span>  
  
 `pDimensionLowerBounds`  
 <span data-ttu-id="e9269-109">out Matrice contenente Integer, ognuno dei quali rappresenta il limite inferiore di una dimensione della matrice.</span><span class="sxs-lookup"><span data-stu-id="e9269-109">[out] An array that contains integers, each representing the lower bound of a dimension of the array.</span></span>  
  
 `ppData`  
 <span data-ttu-id="e9269-110">out Puntatore all'indirizzo del buffer non elaborato per la matrice, disposto in base alla convenzione C++.</span><span class="sxs-lookup"><span data-stu-id="e9269-110">[out] A pointer to the address of the raw buffer for the array, which is laid out according to the C++ convention.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9269-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e9269-111">Remarks</span></span>  
 <span data-ttu-id="e9269-112">`pDimensionSizes`E `pDimensionLowerBounds` sono matrici parallele, pertanto gli elementi che si trovano nello stesso indice in ogni matrice sono caratteristiche della stessa entità.</span><span class="sxs-lookup"><span data-stu-id="e9269-112">The `pDimensionSizes` and `pDimensionLowerBounds` are parallel arrays, so the elements located at the same index in each array are characteristics of the same entity.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9269-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e9269-113">Requirements</span></span>  
 <span data-ttu-id="e9269-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9269-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9269-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e9269-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e9269-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9269-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9269-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9269-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9269-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9269-118">See also</span></span>

- [<span data-ttu-id="e9269-119">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="e9269-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="e9269-120">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="e9269-120">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)

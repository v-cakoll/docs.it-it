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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e6e6f4f6bdfba8deecb3661d88a881759da043ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456307"
---
# <a name="icorprofilerinfo2getarrayobjectinfo-method"></a><span data-ttu-id="9a9f6-102">Metodo ICorProfilerInfo2::GetArrayObjectInfo</span><span class="sxs-lookup"><span data-stu-id="9a9f6-102">ICorProfilerInfo2::GetArrayObjectInfo Method</span></span>
<span data-ttu-id="9a9f6-103">Ottiene informazioni dettagliate su un oggetto matrice.</span><span class="sxs-lookup"><span data-stu-id="9a9f6-103">Gets detailed information about an array object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a9f6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a9f6-104">Syntax</span></span>  
  
```  
HRESULT GetArrayObjectInfo(  
    [in] ObjectID objectId,  
    [in] ULONG32 cDimensions,  
    [out, size_is(cDimensions), length_is(cDimensions)] ULONG32 pDimensionSizes[],  
    [out, size_is(cDimensions), length_is(cDimensions)] int pDimensionLowerBounds[],  
    [out] BYTE **ppData);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a9f6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9a9f6-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="9a9f6-106">[in] L'ID di un oggetto matrice valida.</span><span class="sxs-lookup"><span data-stu-id="9a9f6-106">[in] The ID of a valid array object.</span></span>  
  
 `cDimensions`  
 <span data-ttu-id="9a9f6-107">[in] La classificazione (numero di dimensioni) della matrice.</span><span class="sxs-lookup"><span data-stu-id="9a9f6-107">[in] The rank (number of dimensions) of the array.</span></span>  
  
 `pDimensionSizes`  
 <span data-ttu-id="9a9f6-108">[out] Matrice che contiene numeri interi, ognuno dei quali rappresenta la dimensione di una dimensione della matrice.</span><span class="sxs-lookup"><span data-stu-id="9a9f6-108">[out] An array that contains integers, each representing the size of a dimension of the array.</span></span>  
  
 `pDimensionLowerBounds`  
 <span data-ttu-id="9a9f6-109">[out] Una matrice che contiene numeri interi, ognuno dei quali rappresenta inferiore associato di una dimensione della matrice.</span><span class="sxs-lookup"><span data-stu-id="9a9f6-109">[out] An array that contains integers, each representing the lower bound of a dimension of the array.</span></span>  
  
 `ppData`  
 <span data-ttu-id="9a9f6-110">[out] Un puntatore all'indirizzo del buffer non elaborato per la matrice, che è disposto in base alla convenzione di C++.</span><span class="sxs-lookup"><span data-stu-id="9a9f6-110">[out] A pointer to the address of the raw buffer for the array, which is laid out according to the C++ convention.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a9f6-111">Note</span><span class="sxs-lookup"><span data-stu-id="9a9f6-111">Remarks</span></span>  
 <span data-ttu-id="9a9f6-112">Il `pDimensionSizes` e `pDimensionLowerBounds` sono matrici parallele, pertanto gli elementi in corrispondenza dell'indice stesso in ogni matrice sono caratteristiche della stessa entità.</span><span class="sxs-lookup"><span data-stu-id="9a9f6-112">The `pDimensionSizes` and `pDimensionLowerBounds` are parallel arrays, so the elements located at the same index in each array are characteristics of the same entity.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a9f6-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9a9f6-113">Requirements</span></span>  
 <span data-ttu-id="9a9f6-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a9f6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a9f6-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9a9f6-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9a9f6-116">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="9a9f6-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a9f6-117">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a9f6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a9f6-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a9f6-118">See Also</span></span>  
 [<span data-ttu-id="9a9f6-119">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="9a9f6-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="9a9f6-120">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="9a9f6-120">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)

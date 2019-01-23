---
title: Metodo ICorProfilerInfo4::GetObjectSize2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetObjectSize2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetObjectSize2
helpviewer_keywords:
- GetObjectSize2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetObjectSize2 method [.NET Framework profiling]
ms.assetid: 4a3e43ed-3ee3-4395-ab14-f78b903be13e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9a3b0ddc804e8eefdf90b3b0f17f4575b4d92bf3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54502650"
---
# <a name="icorprofilerinfo4getobjectsize2-method"></a><span data-ttu-id="e5c4f-102">Metodo ICorProfilerInfo4::GetObjectSize2</span><span class="sxs-lookup"><span data-stu-id="e5c4f-102">ICorProfilerInfo4::GetObjectSize2 Method</span></span>
<span data-ttu-id="e5c4f-103">Restituisce le dimensioni di un oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="e5c4f-103">Returns the size of a specified object.</span></span> <span data-ttu-id="e5c4f-104">Sostituisce il [GetObjectSize](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getobjectsize-method.md) metodo segnalando le dimensioni degli oggetti che sono maggiori di quelle che possono essere espresse un `ULONG`.</span><span class="sxs-lookup"><span data-stu-id="e5c4f-104">Replaces the [ICorProfilerInfo::GetObjectSize](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getobjectsize-method.md) method by reporting sizes of objects that are larger than what can be expressed in a `ULONG`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5c4f-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e5c4f-105">Syntax</span></span>  
  
```  
HRESULT GetObjectSize2(  
    [in]  ObjectID objectId,  
    [out] SIZE_T *pcSize);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e5c4f-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="e5c4f-106">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="e5c4f-107">[in] L'ID dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="e5c4f-107">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="e5c4f-108">[out] Puntatore alla dimensione dell'oggetto, in byte.</span><span class="sxs-lookup"><span data-stu-id="e5c4f-108">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5c4f-109">Note</span><span class="sxs-lookup"><span data-stu-id="e5c4f-109">Remarks</span></span>  
 <span data-ttu-id="e5c4f-110">Oggetti diversi dello stesso tipo sono spesso le stesse dimensioni.</span><span class="sxs-lookup"><span data-stu-id="e5c4f-110">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="e5c4f-111">Tuttavia, alcuni tipi, ad esempio le matrici o stringhe, potrebbero essere una dimensione diversa per ogni oggetto.</span><span class="sxs-lookup"><span data-stu-id="e5c4f-111">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5c4f-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e5c4f-112">Requirements</span></span>  
 <span data-ttu-id="e5c4f-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5c4f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5c4f-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e5c4f-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e5c4f-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5c4f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5c4f-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5c4f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5c4f-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5c4f-117">See also</span></span>
- [<span data-ttu-id="e5c4f-118">Interfaccia ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="e5c4f-118">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)

---
title: Metodo ICorProfilerInfo::GetClassFromObject
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromObject
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromObject
helpviewer_keywords:
- GetClassFromObject method [.NET Framework profiling]
- ICorProfilerInfo::GetClassFromObject method [.NET Framework profiling]
ms.assetid: b97493fb-713e-49d5-a73e-5688b2ad0700
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9031ae9b4870c182922baaa41883de4cddb469d2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676679"
---
# <a name="icorprofilerinfogetclassfromobject-method"></a><span data-ttu-id="abecf-102">Metodo ICorProfilerInfo::GetClassFromObject</span><span class="sxs-lookup"><span data-stu-id="abecf-102">ICorProfilerInfo::GetClassFromObject Method</span></span>
<span data-ttu-id="abecf-103">Ottiene il `ClassID` di un oggetto, dato relativo `ObjectID`.</span><span class="sxs-lookup"><span data-stu-id="abecf-103">Gets the `ClassID` of an object, given its `ObjectID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abecf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="abecf-104">Syntax</span></span>  
  
```  
HRESULT GetClassFromObject(  
    [in]  ObjectID objectId,  
    [out] ClassID *pClassId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="abecf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="abecf-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="abecf-106">[in] L'ID dell'oggetto per cui ottenere il `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="abecf-106">[in] The ID of the object for which to get the `ClassID`.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="abecf-107">[out] Un puntatore all'oggetto restituito `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="abecf-107">[out] A pointer to the returned `ClassID`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="abecf-108">Note</span><span class="sxs-lookup"><span data-stu-id="abecf-108">Remarks</span></span>  
 <span data-ttu-id="abecf-109">Un valore null `pClassId` indica che `objectId` dispone di un tipo che lo scaricamento.</span><span class="sxs-lookup"><span data-stu-id="abecf-109">A null `pClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abecf-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="abecf-110">Requirements</span></span>  
 <span data-ttu-id="abecf-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="abecf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abecf-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="abecf-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="abecf-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="abecf-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="abecf-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abecf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abecf-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="abecf-115">See also</span></span>
- [<span data-ttu-id="abecf-116">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="abecf-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)

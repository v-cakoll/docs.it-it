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
ms.openlocfilehash: 460162f0fbc9993635d1bce0c5b130358ced4fa7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448155"
---
# <a name="icorprofilerinfogetclassfromobject-method"></a><span data-ttu-id="c2a07-102">Metodo ICorProfilerInfo::GetClassFromObject</span><span class="sxs-lookup"><span data-stu-id="c2a07-102">ICorProfilerInfo::GetClassFromObject Method</span></span>
<span data-ttu-id="c2a07-103">Gets the `ClassID` of an object, given its `ObjectID`.</span><span class="sxs-lookup"><span data-stu-id="c2a07-103">Gets the `ClassID` of an object, given its `ObjectID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2a07-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c2a07-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromObject(  
    [in]  ObjectID objectId,  
    [out] ClassID *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2a07-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c2a07-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="c2a07-106">[in] The ID of the object for which to get the `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="c2a07-106">[in] The ID of the object for which to get the `ClassID`.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="c2a07-107">[out] A pointer to the returned `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="c2a07-107">[out] A pointer to the returned `ClassID`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2a07-108">Note</span><span class="sxs-lookup"><span data-stu-id="c2a07-108">Remarks</span></span>  
 <span data-ttu-id="c2a07-109">A null `pClassId` indicates that `objectId` has a type that is unloading.</span><span class="sxs-lookup"><span data-stu-id="c2a07-109">A null `pClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2a07-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c2a07-110">Requirements</span></span>  
 <span data-ttu-id="c2a07-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2a07-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2a07-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c2a07-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c2a07-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2a07-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2a07-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2a07-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2a07-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2a07-115">See also</span></span>

- [<span data-ttu-id="c2a07-116">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="c2a07-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)

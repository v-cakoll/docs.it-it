---
title: Metodo ICorProfilerInfo::GetClassIDInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassIDInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassIDInfo
helpviewer_keywords:
- GetClassIDInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetClassIDInfo method [.NET Framework profiling]
ms.assetid: 9e93b99e-5aca-415c-8e37-7f33753b612d
topic_type:
- apiref
ms.openlocfilehash: c3b1bdac8ccd37cf2f6aac5073def313f04acf28
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439239"
---
# <a name="icorprofilerinfogetclassidinfo-method"></a><span data-ttu-id="cb1ef-102">Metodo ICorProfilerInfo::GetClassIDInfo</span><span class="sxs-lookup"><span data-stu-id="cb1ef-102">ICorProfilerInfo::GetClassIDInfo Method</span></span>
<span data-ttu-id="cb1ef-103">Gets the parent module and the metadata token for the specified class.</span><span class="sxs-lookup"><span data-stu-id="cb1ef-103">Gets the parent module and the metadata token for the specified class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb1ef-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cb1ef-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassIDInfo(  
    [in]  ClassID   classId,  
    [out] ModuleID  *pModuleId,  
    [out] mdTypeDef *pTypeDefToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb1ef-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cb1ef-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="cb1ef-106">[in] The ID of the class for which to get the information.</span><span class="sxs-lookup"><span data-stu-id="cb1ef-106">[in] The ID of the class for which to get the information.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="cb1ef-107">[out] A pointer to the ID of the parent module of the class.</span><span class="sxs-lookup"><span data-stu-id="cb1ef-107">[out] A pointer to the ID of the parent module of the class.</span></span>  
  
 `pTypeDefToken`  
 <span data-ttu-id="cb1ef-108">[out] A pointer to the metadata token for the class.</span><span class="sxs-lookup"><span data-stu-id="cb1ef-108">[out] A pointer to the metadata token for the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb1ef-109">Note</span><span class="sxs-lookup"><span data-stu-id="cb1ef-109">Remarks</span></span>  
 <span data-ttu-id="cb1ef-110">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span><span class="sxs-lookup"><span data-stu-id="cb1ef-110">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="cb1ef-111">Il token di metadati restituito al percorso a cui viene fatto riferimento tramite `pTypeDefToken` può quindi essere usato per accedere ai metadati per la classe.</span><span class="sxs-lookup"><span data-stu-id="cb1ef-111">The metadata token that is returned to the location referenced by `pTypeDefToken` can then be used to access the metadata for the class.</span></span>  
  
 <span data-ttu-id="cb1ef-112">To get more information for generic types, use [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md).</span><span class="sxs-lookup"><span data-stu-id="cb1ef-112">To get more information for generic types, use [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb1ef-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cb1ef-113">Requirements</span></span>  
 <span data-ttu-id="cb1ef-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb1ef-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb1ef-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cb1ef-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cb1ef-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb1ef-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb1ef-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb1ef-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb1ef-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb1ef-118">See also</span></span>

- [<span data-ttu-id="cb1ef-119">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="cb1ef-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)

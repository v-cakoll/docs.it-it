---
title: Metodo ICorProfilerInfo::GetClassFromObject
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetClassFromObject
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetClassFromObject
helpviewer_keywords:
- GetClassFromObject method [.NET Framework profiling]
- ICorProfilerInfo::GetClassFromObject method [.NET Framework profiling]
ms.assetid: b97493fb-713e-49d5-a73e-5688b2ad0700
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 706118a197677ec97672cca36f5bcf6421a1c328
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetclassfromobject-method"></a><span data-ttu-id="d7097-102">Metodo ICorProfilerInfo::GetClassFromObject</span><span class="sxs-lookup"><span data-stu-id="d7097-102">ICorProfilerInfo::GetClassFromObject Method</span></span>
<span data-ttu-id="d7097-103">Ottiene il `ClassID` di un oggetto, dato il relativo `ObjectID`.</span><span class="sxs-lookup"><span data-stu-id="d7097-103">Gets the `ClassID` of an object, given its `ObjectID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7097-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d7097-104">Syntax</span></span>  
  
```  
HRESULT GetClassFromObject(  
    [in]  ObjectID objectId,  
    [out] ClassID *pClassId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d7097-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d7097-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="d7097-106">[in] L'ID dell'oggetto per cui ottenere il `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="d7097-106">[in] The ID of the object for which to get the `ClassID`.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="d7097-107">[out] Un puntatore all'oggetto restituito `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="d7097-107">[out] A pointer to the returned `ClassID`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7097-108">Note</span><span class="sxs-lookup"><span data-stu-id="d7097-108">Remarks</span></span>  
 <span data-ttu-id="d7097-109">Un valore null `pClassId` indica che `objectId` dispone di un tipo che lo scaricamento.</span><span class="sxs-lookup"><span data-stu-id="d7097-109">A null `pClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7097-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d7097-110">Requirements</span></span>  
 <span data-ttu-id="d7097-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7097-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7097-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d7097-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d7097-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7097-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7097-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7097-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7097-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7097-115">See Also</span></span>  
 [<span data-ttu-id="d7097-116">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="d7097-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)

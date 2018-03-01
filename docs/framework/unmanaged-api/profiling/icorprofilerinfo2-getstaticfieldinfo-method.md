---
title: Metodo ICorProfilerInfo2::GetStaticFieldInfo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo2.GetStaticFieldInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo method [.NET Framework profiling]
- GetStaticFieldInfo method [.NET Framework profiling]
ms.assetid: fc663e76-e23f-49a8-bdd5-52cdf1a3b2b3
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8a13a07aeb90d7ad05ca83bf273fe999b9a81bd2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getstaticfieldinfo-method"></a><span data-ttu-id="52a22-102">Metodo ICorProfilerInfo2::GetStaticFieldInfo</span><span class="sxs-lookup"><span data-stu-id="52a22-102">ICorProfilerInfo2::GetStaticFieldInfo Method</span></span>
<span data-ttu-id="52a22-103">Ottiene un valore che indica il tipo di valore statico che si applica al campo specificato.</span><span class="sxs-lookup"><span data-stu-id="52a22-103">Gets a value that indicates the kind of static that applies to the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52a22-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="52a22-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldInfo (  
    [in] ClassID               classId,  
    [in] mdFieldDef            fieldToken,  
    [out] COR_PRF_STATIC_TYPE  *pFieldInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="52a22-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="52a22-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="52a22-106">[in] L'ID della classe in cui è definito il campo statico.</span><span class="sxs-lookup"><span data-stu-id="52a22-106">[in] The ID of the class in which the static field is defined.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="52a22-107">[in] Il token di metadati per il campo statico.</span><span class="sxs-lookup"><span data-stu-id="52a22-107">[in] The metadata token for the static field.</span></span>  
  
 `pFieldInfo`  
 <span data-ttu-id="52a22-108">[out] Un puntatore a un valore di [COR_PRF_STATIC_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md) enumerazione che indica se il campo specificato è statico, e se in tal caso, il tipo di valore statico che si applica al campo.</span><span class="sxs-lookup"><span data-stu-id="52a22-108">[out] A pointer to a value of the [COR_PRF_STATIC_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md) enumeration that indicates whether the specified field is static, and if so, the kind of static that applies to the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52a22-109">Note</span><span class="sxs-lookup"><span data-stu-id="52a22-109">Remarks</span></span>  
 <span data-ttu-id="52a22-110">Queste informazioni è utilizzabile per determinare quale funzione chiamare per ottenere l'indirizzo del campo statico.</span><span class="sxs-lookup"><span data-stu-id="52a22-110">This information can be used to determine which function to call to get the address of the static field.</span></span>  
  
 <span data-ttu-id="52a22-111">Il codice del profiler deve comunque verificare i metadati per un campo statico per assicurarsi che sia effettivamente un indirizzo.</span><span class="sxs-lookup"><span data-stu-id="52a22-111">The profiler code should still check the metadata for a static field to ensure that it actually has an address.</span></span> <span data-ttu-id="52a22-112">Valori letterali statici (ovvero, costanti) esistono solo nei metadati e non hanno un indirizzo.</span><span class="sxs-lookup"><span data-stu-id="52a22-112">Static literals (that is, constants) exist only in the metadata and do not have an address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52a22-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="52a22-113">Requirements</span></span>  
 <span data-ttu-id="52a22-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52a22-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52a22-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="52a22-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="52a22-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52a22-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52a22-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52a22-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52a22-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52a22-118">See Also</span></span>  
 [<span data-ttu-id="52a22-119">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="52a22-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="52a22-120">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="52a22-120">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)

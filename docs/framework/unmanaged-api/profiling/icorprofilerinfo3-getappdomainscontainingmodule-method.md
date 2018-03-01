---
title: Metodo ICorProfilerInfo3::GetAppDomainsContainingModule
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
- ICorProfilerInfo3.GetAppDomainsContainingModule Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetAppDomainsContainingModule
helpviewer_keywords:
- GetAppDomainsContainingModule method [.NET Framework profiling]
- ICorProfilerInfo3::GetAppDomainsContainingModule method [.NET Framework profiling]
ms.assetid: 603b3881-ea94-4dca-95cd-91eebac873a0
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fa0aa6620f8465154ac31586618af3fe36f3dfe4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo3getappdomainscontainingmodule-method"></a><span data-ttu-id="ae778-102">Metodo ICorProfilerInfo3::GetAppDomainsContainingModule</span><span class="sxs-lookup"><span data-stu-id="ae778-102">ICorProfilerInfo3::GetAppDomainsContainingModule Method</span></span>
<span data-ttu-id="ae778-103">Ottiene gli identificatori dei domini dell'applicazione in cui è stato caricato il modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="ae778-103">Gets the identifiers of the application domains in which the given module has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae778-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ae778-104">Syntax</span></span>  
  
```  
HRESULT GetAppDomainsContainingModule(  
            [in] ModuleID moduleId,  
            [in] ULONG32 cAppDomainIds,  
            [out] ULONG32 *pcAppDomainIds,  
            [out, size_is(cAppDomainIds), length_is(*pcAppDomainIds)]  
                    AppDomainID appDomainIds[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ae778-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ae778-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="ae778-106">[in] ID del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="ae778-106">[in] The ID of the loaded module.</span></span>  
  
 `cAppDomainIds`  
 <span data-ttu-id="ae778-107">[in] Dimensione della matrice `appDomainIds`.</span><span class="sxs-lookup"><span data-stu-id="ae778-107">[in] The size of the `appDomainIds` array.</span></span>  
  
 `pcAppDomainIds`  
 <span data-ttu-id="ae778-108">[out] Puntatore al numero complessivo di elementi restituiti.</span><span class="sxs-lookup"><span data-stu-id="ae778-108">[out] A pointer to the total number of returned elements.</span></span>  
  
 `appDomainIds`  
 <span data-ttu-id="ae778-109">[out] Matrice di valori di valori di ID del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="ae778-109">[out] An array of application domain ID values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae778-110">Note</span><span class="sxs-lookup"><span data-stu-id="ae778-110">Remarks</span></span>  
 <span data-ttu-id="ae778-111">Il metodo usa buffer allocati dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="ae778-111">The method uses caller allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae778-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ae778-112">Requirements</span></span>  
 <span data-ttu-id="ae778-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae778-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae778-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ae778-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ae778-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae778-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae778-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae778-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae778-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae778-117">See Also</span></span>  
 [<span data-ttu-id="ae778-118">Interfaccia ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="ae778-118">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 [<span data-ttu-id="ae778-119">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="ae778-119">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="ae778-120">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="ae778-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="ae778-121">Profilatura</span><span class="sxs-lookup"><span data-stu-id="ae778-121">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)

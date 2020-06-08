---
title: Metodo ICorProfilerInfo3::GetAppDomainsContainingModule
ms.date: 03/30/2017
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
ms.openlocfilehash: 8615deb2e42b039120d97b3eb5af23beb31b0808
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502847"
---
# <a name="icorprofilerinfo3getappdomainscontainingmodule-method"></a><span data-ttu-id="4b5c3-102">Metodo ICorProfilerInfo3::GetAppDomainsContainingModule</span><span class="sxs-lookup"><span data-stu-id="4b5c3-102">ICorProfilerInfo3::GetAppDomainsContainingModule Method</span></span>
<span data-ttu-id="4b5c3-103">Ottiene gli identificatori dei domini dell'applicazione in cui è stato caricato il modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-103">Gets the identifiers of the application domains in which the given module has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b5c3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4b5c3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomainsContainingModule(  
            [in] ModuleID moduleId,  
            [in] ULONG32 cAppDomainIds,  
            [out] ULONG32 *pcAppDomainIds,  
            [out, size_is(cAppDomainIds), length_is(*pcAppDomainIds)]  
                    AppDomainID appDomainIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b5c3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4b5c3-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="4b5c3-106">[in] ID del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-106">[in] The ID of the loaded module.</span></span>  
  
 `cAppDomainIds`  
 <span data-ttu-id="4b5c3-107">[in] Dimensione della matrice `appDomainIds`.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-107">[in] The size of the `appDomainIds` array.</span></span>  
  
 `pcAppDomainIds`  
 <span data-ttu-id="4b5c3-108">[out] Puntatore al numero complessivo di elementi restituiti.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-108">[out] A pointer to the total number of returned elements.</span></span>  
  
 `appDomainIds`  
 <span data-ttu-id="4b5c3-109">[out] Matrice di valori di valori di ID del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-109">[out] An array of application domain ID values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b5c3-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4b5c3-110">Remarks</span></span>  
 <span data-ttu-id="4b5c3-111">Il metodo usa buffer allocati dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="4b5c3-111">The method uses caller allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b5c3-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4b5c3-112">Requirements</span></span>  
 <span data-ttu-id="4b5c3-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b5c3-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b5c3-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4b5c3-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4b5c3-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b5c3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b5c3-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b5c3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b5c3-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b5c3-117">See also</span></span>

- [<span data-ttu-id="4b5c3-118">Interfaccia ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="4b5c3-118">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="4b5c3-119">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="4b5c3-119">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="4b5c3-120">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="4b5c3-120">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="4b5c3-121">Profilatura</span><span class="sxs-lookup"><span data-stu-id="4b5c3-121">Profiling</span></span>](index.md)

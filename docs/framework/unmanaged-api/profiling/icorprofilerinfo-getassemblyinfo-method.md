---
title: Metodo ICorProfilerInfo::GetAssemblyInfo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetAssemblyInfo
api_location: mscorwks.dll
api_type: COM
f1_keywords: GetAssemblyInfo Method
helpviewer_keywords:
- GetAssemblyInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetAssemblyInfo method [.NET Framework profiling]
ms.assetid: 7a3c97c3-1e31-47b1-bf23-386785c509c4
topic_type: apiref
caps.latest.revision: "20"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f3ac5bd35d12bb4c9d9308dcdff3e1fb8385f6f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetassemblyinfo-method"></a><span data-ttu-id="8bb0c-102">Metodo ICorProfilerInfo::GetAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="8bb0c-102">ICorProfilerInfo::GetAssemblyInfo Method</span></span>
<span data-ttu-id="8bb0c-103">Accetta l'ID di un assembly e restituisce il nome dell'assembly e l'ID del relativo modulo del manifesto.</span><span class="sxs-lookup"><span data-stu-id="8bb0c-103">Accepts an assembly ID, and returns the assembly's name and the ID of its manifest module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bb0c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8bb0c-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyInfo(  
    [in]  AssemblyID  assemblyId,  
    [in]  ULONG       cchName,  
    [out] ULONG       *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR       szName[] ,  
    [out] AppDomainID *pAppDomainId,  
    [out] ModuleID    *pModuleId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8bb0c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8bb0c-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="8bb0c-106">[in] Identificatore dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="8bb0c-106">[in] The identifier of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="8bb0c-107">[in] Lunghezza del parametro `szName` in caratteri.</span><span class="sxs-lookup"><span data-stu-id="8bb0c-107">[in] The length, in characters, of `szName`.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="8bb0c-108">[out] Puntatore ai caratteri totali del nome dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="8bb0c-108">[out] A pointer to the total character length of the assembly's name.</span></span>  
  
 `szName`  
 <span data-ttu-id="8bb0c-109">[out] Buffer per caratteri di tipo "wide" fornito dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="8bb0c-109">[out] A caller-provided wide character buffer.</span></span> <span data-ttu-id="8bb0c-110">Una volta completata, la funzione conterrà il nome dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="8bb0c-110">When the function returns, it will contain the assembly's name.</span></span>  
  
 `pAppDomainId`  
 <span data-ttu-id="8bb0c-111">[out] Puntatore all'ID del dominio dell'applicazione che contiene l'assembly.</span><span class="sxs-lookup"><span data-stu-id="8bb0c-111">[out] A pointer to the ID of the application domain that contains the assembly.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="8bb0c-112">[out] Puntatore all'ID del modulo del manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="8bb0c-112">[out] A pointer to the ID of the assembly's manifest module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8bb0c-113">Note</span><span class="sxs-lookup"><span data-stu-id="8bb0c-113">Remarks</span></span>  
 <span data-ttu-id="8bb0c-114">Quando il metodo viene completato, è necessario verificare che il buffer `szName` sia abbastanza grande per contenere il nome completo dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="8bb0c-114">After this method returns, you must verify that the `szName` buffer was large enough to contain the full name of the assembly.</span></span> <span data-ttu-id="8bb0c-115">A tale scopo, confrontare il valore a cui punta `pcchName` con il valore del parametro `cchName`.</span><span class="sxs-lookup"><span data-stu-id="8bb0c-115">To do this, compare the value that `pcchName` points to with the value of the `cchName` parameter.</span></span> <span data-ttu-id="8bb0c-116">Se `pcchName` punta a un valore maggiore di `cchName`, allocare un buffer `szName` più grande, aggiornare `cchName` con la nuova dimensione e chiamare nuovamente `GetAssemblyInfo`.</span><span class="sxs-lookup"><span data-stu-id="8bb0c-116">If `pcchName` points to a value that is larger than `cchName`, allocate a larger `szName` buffer, update `cchName` with the new, larger size, and call `GetAssemblyInfo` again.</span></span>  
  
 <span data-ttu-id="8bb0c-117">In alternativa, è possibile chiamare innanzitutto `GetAssemblyInfo` con un buffer `szName` di lunghezza zero per ottenere le dimensioni del buffer corrette.</span><span class="sxs-lookup"><span data-stu-id="8bb0c-117">Alternatively, you can first call `GetAssemblyInfo` with a zero-length `szName` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="8bb0c-118">È quindi possibile impostare le dimensioni del buffer sul valore restituito in `pcchName` e chiamare nuovamente `GetAssemblyInfo`.</span><span class="sxs-lookup"><span data-stu-id="8bb0c-118">You can then adjust the buffer size based on the value returned in `pcchName` and call `GetAssemblyInfo` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bb0c-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8bb0c-119">Requirements</span></span>  
 <span data-ttu-id="8bb0c-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8bb0c-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bb0c-121">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8bb0c-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8bb0c-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8bb0c-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8bb0c-123">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bb0c-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bb0c-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8bb0c-124">See Also</span></span>  
 [<span data-ttu-id="8bb0c-125">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="8bb0c-125">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="8bb0c-126">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="8bb0c-126">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="8bb0c-127">Profilatura</span><span class="sxs-lookup"><span data-stu-id="8bb0c-127">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)

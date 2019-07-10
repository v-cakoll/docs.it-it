---
title: Metodo ICorProfilerInfo::GetAssemblyInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetAssemblyInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- GetAssemblyInfo Method
helpviewer_keywords:
- GetAssemblyInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetAssemblyInfo method [.NET Framework profiling]
ms.assetid: 7a3c97c3-1e31-47b1-bf23-386785c509c4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0b410ef46e96f75d98ee750c760b19d2a77eec2b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780209"
---
# <a name="icorprofilerinfogetassemblyinfo-method"></a><span data-ttu-id="83787-102">Metodo ICorProfilerInfo::GetAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="83787-102">ICorProfilerInfo::GetAssemblyInfo Method</span></span>
<span data-ttu-id="83787-103">Accetta l'ID di un assembly e restituisce il nome dell'assembly e l'ID del relativo modulo del manifesto.</span><span class="sxs-lookup"><span data-stu-id="83787-103">Accepts an assembly ID, and returns the assembly's name and the ID of its manifest module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83787-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="83787-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyInfo(  
    [in]  AssemblyID  assemblyId,  
    [in]  ULONG       cchName,  
    [out] ULONG       *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR       szName[] ,  
    [out] AppDomainID *pAppDomainId,  
    [out] ModuleID    *pModuleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83787-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="83787-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="83787-106">[in] Identificatore dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="83787-106">[in] The identifier of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="83787-107">[in] Lunghezza del parametro `szName` in caratteri.</span><span class="sxs-lookup"><span data-stu-id="83787-107">[in] The length, in characters, of `szName`.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="83787-108">[out] Puntatore ai caratteri totali del nome dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="83787-108">[out] A pointer to the total character length of the assembly's name.</span></span>  
  
 `szName`  
 <span data-ttu-id="83787-109">[out] Buffer per caratteri di tipo "wide" fornito dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="83787-109">[out] A caller-provided wide character buffer.</span></span> <span data-ttu-id="83787-110">Una volta completata, la funzione conterrà il nome dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="83787-110">When the function returns, it will contain the assembly's name.</span></span>  
  
 `pAppDomainId`  
 <span data-ttu-id="83787-111">[out] Puntatore all'ID del dominio dell'applicazione che contiene l'assembly.</span><span class="sxs-lookup"><span data-stu-id="83787-111">[out] A pointer to the ID of the application domain that contains the assembly.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="83787-112">[out] Puntatore all'ID del modulo del manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="83787-112">[out] A pointer to the ID of the assembly's manifest module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83787-113">Note</span><span class="sxs-lookup"><span data-stu-id="83787-113">Remarks</span></span>  
 <span data-ttu-id="83787-114">Quando il metodo viene completato, è necessario verificare che il buffer `szName` sia abbastanza grande per contenere il nome completo dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="83787-114">After this method returns, you must verify that the `szName` buffer was large enough to contain the full name of the assembly.</span></span> <span data-ttu-id="83787-115">A tale scopo, confrontare il valore a cui punta `pcchName` con il valore del parametro `cchName`.</span><span class="sxs-lookup"><span data-stu-id="83787-115">To do this, compare the value that `pcchName` points to with the value of the `cchName` parameter.</span></span> <span data-ttu-id="83787-116">Se `pcchName` punta a un valore maggiore di `cchName`, allocare un buffer `szName` più grande, aggiornare `cchName` con la nuova dimensione e chiamare nuovamente `GetAssemblyInfo`.</span><span class="sxs-lookup"><span data-stu-id="83787-116">If `pcchName` points to a value that is larger than `cchName`, allocate a larger `szName` buffer, update `cchName` with the new, larger size, and call `GetAssemblyInfo` again.</span></span>  
  
 <span data-ttu-id="83787-117">In alternativa, è possibile chiamare innanzitutto `GetAssemblyInfo` con un buffer `szName` di lunghezza zero per ottenere le dimensioni del buffer corrette.</span><span class="sxs-lookup"><span data-stu-id="83787-117">Alternatively, you can first call `GetAssemblyInfo` with a zero-length `szName` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="83787-118">È quindi possibile impostare le dimensioni del buffer sul valore restituito in `pcchName` e chiamare nuovamente `GetAssemblyInfo`.</span><span class="sxs-lookup"><span data-stu-id="83787-118">You can then adjust the buffer size based on the value returned in `pcchName` and call `GetAssemblyInfo` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83787-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="83787-119">Requirements</span></span>  
 <span data-ttu-id="83787-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83787-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83787-121">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="83787-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="83787-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83787-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83787-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83787-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83787-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83787-124">See also</span></span>

- [<span data-ttu-id="83787-125">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="83787-125">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="83787-126">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="83787-126">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="83787-127">Profilatura</span><span class="sxs-lookup"><span data-stu-id="83787-127">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)

---
title: Metodo ICorProfilerInfo::GetModuleInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetModuleInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetModuleInfo
helpviewer_keywords:
- GetModuleInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleInfo method [.NET Framework profiling]
ms.assetid: 5a90d16f-7929-4987-8f83-a631becf564d
topic_type:
- apiref
ms.openlocfilehash: 751f2ac44e543fed76c7031791bb57d75ed0fd48
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498102"
---
# <a name="icorprofilerinfogetmoduleinfo-method"></a><span data-ttu-id="fd2f9-102">Metodo ICorProfilerInfo::GetModuleInfo</span><span class="sxs-lookup"><span data-stu-id="fd2f9-102">ICorProfilerInfo::GetModuleInfo Method</span></span>
<span data-ttu-id="fd2f9-103">Dato un ID modulo, restituisce il nome file del modulo e l'ID dell'assembly padre del modulo.</span><span class="sxs-lookup"><span data-stu-id="fd2f9-103">Given a module ID, returns the file name of the module and the ID of the module's parent assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd2f9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fd2f9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleInfo(  
    [in]  ModuleID   moduleId,  
    [out] LPCBYTE    *ppBaseLoadAddress,  
    [in]  ULONG      cchName,  
    [out] ULONG      *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR      szName[] ,  
    [out] AssemblyID *pAssemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd2f9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fd2f9-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="fd2f9-106">[in] ID del modulo per cui verranno recuperate informazioni.</span><span class="sxs-lookup"><span data-stu-id="fd2f9-106">[in] The ID of the module for which information will be retrieved.</span></span>  
  
 `ppBaseLoadAddress`  
 <span data-ttu-id="fd2f9-107">[out] Indirizzo di base in cui viene caricato il modulo.</span><span class="sxs-lookup"><span data-stu-id="fd2f9-107">[out] The base address at which the module is loaded.</span></span>  
  
 `cchName`  
 <span data-ttu-id="fd2f9-108">[in] Lunghezza, espressa in caratteri, del buffer restituito `szName`.</span><span class="sxs-lookup"><span data-stu-id="fd2f9-108">[in] The length, in characters, of the `szName` return buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="fd2f9-109">[out] Puntatore alla lunghezza totale in caratteri del nome file del modulo che viene restituito.</span><span class="sxs-lookup"><span data-stu-id="fd2f9-109">[out] A pointer to the total character length of the module's file name that is returned.</span></span>  
  
 `szName`  
 <span data-ttu-id="fd2f9-110">[out] Buffer per caratteri di tipo "wide" fornito dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="fd2f9-110">[out] A caller-provided wide character buffer.</span></span> <span data-ttu-id="fd2f9-111">Quando il metodo viene completato, questo buffer contiene il nome file del modulo.</span><span class="sxs-lookup"><span data-stu-id="fd2f9-111">When the method returns, this buffer contains the file name of the module.</span></span>  
  
 `pAssemblyId`  
 <span data-ttu-id="fd2f9-112">[out] Puntatore all'ID dell'assembly padre del modulo.</span><span class="sxs-lookup"><span data-stu-id="fd2f9-112">[out] A pointer to the ID of the module's parent assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd2f9-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="fd2f9-113">Remarks</span></span>  
 <span data-ttu-id="fd2f9-114">Per i moduli dinamici, il parametro `szName` è una stringa vuota e l'indirizzo di base è 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="fd2f9-114">For dynamic modules, the `szName` parameter is an empty string, and the base address is 0 (zero).</span></span>  
  
 <span data-ttu-id="fd2f9-115">Sebbene il `GetModuleInfo` metodo possa essere chiamato non appena l'ID del modulo esiste, l'ID dell'assembly padre non sarà disponibile fino a quando il profiler non riceve il callback [ICorProfilerCallback:: ModuleAttachedToAssembly](icorprofilercallback-moduleattachedtoassembly-method.md) .</span><span class="sxs-lookup"><span data-stu-id="fd2f9-115">Although the `GetModuleInfo` method may be called as soon as the module's ID exists, the ID of the parent assembly will not be available until the profiler receives the [ICorProfilerCallback::ModuleAttachedToAssembly](icorprofilercallback-moduleattachedtoassembly-method.md) callback.</span></span>  
  
 <span data-ttu-id="fd2f9-116">Dopo il completamento del metodo `GetModuleInfo`, è necessario verificare che il buffer `szName` sia abbastanza grande per contenere il nome file completo del modulo.</span><span class="sxs-lookup"><span data-stu-id="fd2f9-116">When `GetModuleInfo` returns, you must verify that the `szName` buffer was large enough to contain the full file name of the module.</span></span> <span data-ttu-id="fd2f9-117">A tale scopo, confrontare il valore a cui punta `pcchName` con il valore del parametro `cchName`.</span><span class="sxs-lookup"><span data-stu-id="fd2f9-117">To do this, compare the value that `pcchName` points to with the value of the `cchName` parameter.</span></span> <span data-ttu-id="fd2f9-118">Se `pcchName` punta a un valore maggiore di `cchName`, allocare un buffer `szName` più grande, aggiornare `cchName` con la nuova dimensione e chiamare nuovamente `GetModuleInfo`.</span><span class="sxs-lookup"><span data-stu-id="fd2f9-118">If `pcchName` points to a value that is larger than `cchName`, allocate a larger `szName` buffer, update `cchName` with the new, larger size, and call `GetModuleInfo` again.</span></span>  
  
 <span data-ttu-id="fd2f9-119">In alternativa, è possibile chiamare innanzitutto `GetModuleInfo` con un buffer `szName` di lunghezza zero per ottenere le dimensioni del buffer corrette.</span><span class="sxs-lookup"><span data-stu-id="fd2f9-119">Alternatively, you can first call `GetModuleInfo` with a zero-length `szName` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="fd2f9-120">È quindi possibile impostare le dimensioni del buffer sul valore restituito nel parametro `pcchName` e chiamare nuovamente `GetModuleInfo`.</span><span class="sxs-lookup"><span data-stu-id="fd2f9-120">You can then set the buffer size to the value returned in `pcchName` and call `GetModuleInfo` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd2f9-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fd2f9-121">Requirements</span></span>  
 <span data-ttu-id="fd2f9-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd2f9-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd2f9-123">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fd2f9-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fd2f9-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd2f9-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd2f9-125">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd2f9-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd2f9-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd2f9-126">See also</span></span>

- [<span data-ttu-id="fd2f9-127">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="fd2f9-127">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="fd2f9-128">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="fd2f9-128">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="fd2f9-129">Profilatura</span><span class="sxs-lookup"><span data-stu-id="fd2f9-129">Profiling</span></span>](index.md)
- [<span data-ttu-id="fd2f9-130">Metodo GetModuleInfo2</span><span class="sxs-lookup"><span data-stu-id="fd2f9-130">GetModuleInfo2 Method</span></span>](icorprofilerinfo3-getmoduleinfo2-method.md)

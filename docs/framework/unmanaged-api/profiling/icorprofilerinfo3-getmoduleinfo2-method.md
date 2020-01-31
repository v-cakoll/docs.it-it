---
title: Metodo ICorProfilerInfo3::GetModuleInfo2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetModuleInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetModuleInfo2
helpviewer_keywords:
- ICorProfilerInfo3::GetModuleInfo2 method [.NET Framework profiling]
- GetModuleInfo2 method [.NET Framework profiling]
ms.assetid: f1f6b8f3-dcfc-49e8-be76-ea50ea90d5a7
topic_type:
- apiref
ms.openlocfilehash: 96cde35c7151bb7ce58715f2826feaa59b30efab
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862308"
---
# <a name="icorprofilerinfo3getmoduleinfo2-method"></a><span data-ttu-id="aa77a-102">Metodo ICorProfilerInfo3::GetModuleInfo2</span><span class="sxs-lookup"><span data-stu-id="aa77a-102">ICorProfilerInfo3::GetModuleInfo2 Method</span></span>
<span data-ttu-id="aa77a-103">Dato un ID modulo, restituisce il nome file del modulo, l'ID dell'assembly padre del modulo e una maschera di bit che descrive le proprietà del modulo.</span><span class="sxs-lookup"><span data-stu-id="aa77a-103">Given a module ID, returns the file name of the module, the ID of the module's parent assembly, and a bitmask that describes the properties of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa77a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aa77a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleInfo2(  
    [in]  ModuleID   moduleId,  
    [out] LPCBYTE    *ppBaseLoadAddress,  
    [in]  ULONG      cchName,  
    [out] ULONG      *pcchName,  
    [out, annotation("__out_ecount_part(cchName, *pcchName)")]  
          WCHAR      szName[] ,  
    [out] AssemblyID *pAssemblyId);  
    [out] DWORD                 *pdwModuleFlags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa77a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="aa77a-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="aa77a-106">[in] ID del modulo per cui verranno recuperate informazioni.</span><span class="sxs-lookup"><span data-stu-id="aa77a-106">[in] The ID of the module for which information will be retrieved.</span></span>  
  
 `ppBaseLoadAddress`  
 <span data-ttu-id="aa77a-107">[out] Indirizzo di base in cui viene caricato il modulo.</span><span class="sxs-lookup"><span data-stu-id="aa77a-107">[out] The base address at which the module is loaded.</span></span>  
  
 `cchName`  
 <span data-ttu-id="aa77a-108">[in] Lunghezza, espressa in caratteri, del buffer restituito `szName`.</span><span class="sxs-lookup"><span data-stu-id="aa77a-108">[in] The length, in characters, of the `szName` return buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="aa77a-109">[out] Puntatore alla lunghezza totale in caratteri del nome file del modulo che viene restituito.</span><span class="sxs-lookup"><span data-stu-id="aa77a-109">[out] A pointer to the total character length of the module's file name that is returned.</span></span>  
  
 `szName`  
 <span data-ttu-id="aa77a-110">[out] Buffer per caratteri di tipo "wide" fornito dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="aa77a-110">[out] A caller-provided wide character buffer.</span></span> <span data-ttu-id="aa77a-111">Quando il metodo viene completato, questo buffer contiene il nome file del modulo.</span><span class="sxs-lookup"><span data-stu-id="aa77a-111">When the method returns, this buffer contains the file name of the module.</span></span>  
  
 `pAssemblyId`  
 <span data-ttu-id="aa77a-112">[out] Puntatore all'ID dell'assembly padre del modulo.</span><span class="sxs-lookup"><span data-stu-id="aa77a-112">[out] A pointer to the ID of the module's parent assembly.</span></span>  
  
 `pdwModuleFlags`  
 <span data-ttu-id="aa77a-113">out Maschera di maschera dei valori dell'enumerazione [COR_PRF_MODULE_FLAGS](cor-prf-module-flags-enumeration.md) che specificano le proprietà del modulo.</span><span class="sxs-lookup"><span data-stu-id="aa77a-113">[out] A bitmask of values from the [COR_PRF_MODULE_FLAGS](cor-prf-module-flags-enumeration.md) enumeration that specify the properties of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa77a-114">Note</span><span class="sxs-lookup"><span data-stu-id="aa77a-114">Remarks</span></span>  
 <span data-ttu-id="aa77a-115">Per i moduli dinamici, il parametro `szName` è il nome di metadati del modulo e l'indirizzo di base è 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="aa77a-115">For dynamic modules, the `szName` parameter is the metadata name of the module, and the base address is 0 (zero).</span></span> <span data-ttu-id="aa77a-116">Il nome dei metadati è il valore nella colonna Name dalla tabella Module all'interno dei metadati.</span><span class="sxs-lookup"><span data-stu-id="aa77a-116">The metadata name is the value in the Name column from the Module table inside metadata.</span></span> <span data-ttu-id="aa77a-117">Viene anche esposto come proprietà <xref:System.Reflection.Module.ScopeName%2A?displayProperty=nameWithType> al codice gestito e come parametro di `szName` del metodo [IMetaDataImport:: GetScopeProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getscopeprops-method.md) al codice client dei metadati non gestiti.</span><span class="sxs-lookup"><span data-stu-id="aa77a-117">This is also exposed as the <xref:System.Reflection.Module.ScopeName%2A?displayProperty=nameWithType> property to managed code, and as the `szName` parameter of the [IMetaDataImport::GetScopeProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getscopeprops-method.md) method to unmanaged metadata client code.</span></span>  
  
 <span data-ttu-id="aa77a-118">Sebbene il metodo `GetModuleInfo2` possa essere chiamato non appena l'ID del modulo esiste, l'ID dell'assembly padre non sarà disponibile fino a quando il profiler non riceve il callback [ICorProfilerCallback:: ModuleAttachedToAssembly](icorprofilercallback-moduleattachedtoassembly-method.md) .</span><span class="sxs-lookup"><span data-stu-id="aa77a-118">Although the `GetModuleInfo2` method may be called as soon as the module's ID exists, the ID of the parent assembly will not be available until the profiler receives the [ICorProfilerCallback::ModuleAttachedToAssembly](icorprofilercallback-moduleattachedtoassembly-method.md) callback.</span></span>  
  
 <span data-ttu-id="aa77a-119">Dopo il completamento del metodo `GetModuleInfo2`, è necessario verificare che il buffer `szName` sia abbastanza grande per contenere il nome file completo del modulo.</span><span class="sxs-lookup"><span data-stu-id="aa77a-119">When `GetModuleInfo2` returns, you must verify that the `szName` buffer was large enough to contain the full file name of the module.</span></span> <span data-ttu-id="aa77a-120">A tale scopo, confrontare il valore a cui punta `pcchName` con il valore del parametro `cchName`.</span><span class="sxs-lookup"><span data-stu-id="aa77a-120">To do this, compare the value that `pcchName` points to with the value of the `cchName` parameter.</span></span> <span data-ttu-id="aa77a-121">Se `pcchName` punta a un valore maggiore di `cchName`, allocare un buffer `szName` più grande, aggiornare `cchName` con la nuova dimensione e chiamare nuovamente `GetModuleInfo2`.</span><span class="sxs-lookup"><span data-stu-id="aa77a-121">If `pcchName` points to a value that is larger than `cchName`, allocate a larger `szName` buffer, update `cchName` with the new, larger size, and call `GetModuleInfo2` again.</span></span>  
  
 <span data-ttu-id="aa77a-122">In alternativa, è possibile chiamare innanzitutto `GetModuleInfo2` con un buffer `szName` di lunghezza zero per ottenere le dimensioni del buffer corrette.</span><span class="sxs-lookup"><span data-stu-id="aa77a-122">Alternatively, you can first call `GetModuleInfo2` with a zero-length `szName` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="aa77a-123">È quindi possibile impostare le dimensioni del buffer sul valore restituito nel parametro `pcchName` e chiamare nuovamente `GetModuleInfo2`.</span><span class="sxs-lookup"><span data-stu-id="aa77a-123">You can then set the buffer size to the value returned in `pcchName` and call `GetModuleInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa77a-124">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="aa77a-124">Requirements</span></span>  
 <span data-ttu-id="aa77a-125">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa77a-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa77a-126">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="aa77a-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="aa77a-127">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa77a-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa77a-128">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa77a-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa77a-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa77a-129">See also</span></span>

- [<span data-ttu-id="aa77a-130">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="aa77a-130">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="aa77a-131">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="aa77a-131">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="aa77a-132">Profilatura</span><span class="sxs-lookup"><span data-stu-id="aa77a-132">Profiling</span></span>](index.md)

---
title: Metodo ICorProfilerInfo2::GetClassIDInfo2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassIDInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassIDInfo2
helpviewer_keywords:
- GetClassIDInfo2 method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassIDInfo2 method [.NET Framework profiling]
ms.assetid: 0141d582-d066-4d49-8d1f-ae82129a1960
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7b98746be189e211572e5517aac1f06825973b39
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59168863"
---
# <a name="icorprofilerinfo2getclassidinfo2-method"></a><span data-ttu-id="0fcd2-102">Metodo ICorProfilerInfo2::GetClassIDInfo2</span><span class="sxs-lookup"><span data-stu-id="0fcd2-102">ICorProfilerInfo2::GetClassIDInfo2 Method</span></span>
<span data-ttu-id="0fcd2-103">Ottiene il modulo padre e i metadati token per aprirla definizione generica della classe specificata, il `ClassID` della relativa classe padre e il `ClassID` per ogni argomento di tipo, se presente, della classe.</span><span class="sxs-lookup"><span data-stu-id="0fcd2-103">Gets the parent module and metadata token for the open generic definition of the specified class, the `ClassID` of its parent class, and the `ClassID` for each type argument, if present, of the class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fcd2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0fcd2-104">Syntax</span></span>  
  
```  
HRESULT GetClassIDInfo2(  
    [in]  ClassID classId,  
    [out] ModuleID *pModuleId,  
    [out] mdTypeDef *pTypeDefToken,  
    [out] ClassID *pParentClassId,  
    [in]  ULONG32 cNumTypeArgs,  
    [out] ULONG32 *pcNumTypeArgs,  
    [out] ClassID typeArgs[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0fcd2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0fcd2-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="0fcd2-106">[in] ID della classe per la quale verranno recuperate le informazioni.</span><span class="sxs-lookup"><span data-stu-id="0fcd2-106">[in] The ID of the class for which information will be retrieved.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="0fcd2-107">[out] Puntatore all'ID del modulo padre per la definizione generica aperta della classe specificata.</span><span class="sxs-lookup"><span data-stu-id="0fcd2-107">[out] Pointer to the ID of the parent module for the open generic definition of the specified class.</span></span>  
  
 `pTypeDefToken`  
 <span data-ttu-id="0fcd2-108">[out] Puntatore al token di metadati per la definizione generica aperta della classe specificata.</span><span class="sxs-lookup"><span data-stu-id="0fcd2-108">[out] Pointer to the metadata token for the open generic definition of the specified class.</span></span>  
  
 `pParentClassId`  
 <span data-ttu-id="0fcd2-109">[out] Puntatore all'ID della classe padre.</span><span class="sxs-lookup"><span data-stu-id="0fcd2-109">[out] Pointer to the ID of the parent class.</span></span>  
  
 `cNumTypeArgs`  
 <span data-ttu-id="0fcd2-110">[in] Dimensione della matrice `typeArgs`.</span><span class="sxs-lookup"><span data-stu-id="0fcd2-110">[in] The size of the `typeArgs` array.</span></span>  
  
 `pcNumTypeArgs`  
 <span data-ttu-id="0fcd2-111">[out] Puntatore al numero complessivo di elementi disponibili.</span><span class="sxs-lookup"><span data-stu-id="0fcd2-111">[out] Pointer to the total number of available elements.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="0fcd2-112">[out] Matrice di valori `ClassID`, ognuno dei quali rappresenta l'ID di un argomento di tipo della classe.</span><span class="sxs-lookup"><span data-stu-id="0fcd2-112">[out] An array of `ClassID` values, each of which represents the ID of a type argument of the class.</span></span> <span data-ttu-id="0fcd2-113">Quando il metodo restituisce i risultati, `typeArgs` conterrà alcuni o tutti i valori `ClassID` disponibili.</span><span class="sxs-lookup"><span data-stu-id="0fcd2-113">When the method returns, `typeArgs` will contain some or all the available `ClassID` values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0fcd2-114">Note</span><span class="sxs-lookup"><span data-stu-id="0fcd2-114">Remarks</span></span>  
 <span data-ttu-id="0fcd2-115">Il `GetClassIDInfo2` metodo è simile al [ICorProfilerInfo:: GetClassIDInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md) metodo, ma `GetClassIDInfo2` Ottiene informazioni aggiuntive su un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="0fcd2-115">The `GetClassIDInfo2` method is similar to the [ICorProfilerInfo::GetClassIDInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md) method, but `GetClassIDInfo2` obtains additional information about a generic type.</span></span>  
  
 <span data-ttu-id="0fcd2-116">Il codice del profiler può chiamare [ICorProfilerInfo:: GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) per ottenere un [metadati](../../../../docs/framework/unmanaged-api/metadata/index.md) interfaccia per un determinato modulo.</span><span class="sxs-lookup"><span data-stu-id="0fcd2-116">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a [metadata](../../../../docs/framework/unmanaged-api/metadata/index.md) interface for a given module.</span></span> <span data-ttu-id="0fcd2-117">Il token di metadati restituito al percorso a cui viene fatto riferimento tramite `pTypeDefToken` può quindi essere usato per accedere ai metadati per la classe.</span><span class="sxs-lookup"><span data-stu-id="0fcd2-117">The metadata token that is returned to the location referenced by `pTypeDefToken` can then be used to access the metadata for the class.</span></span>  
  
 <span data-ttu-id="0fcd2-118">Dopo il completamento del metodo `GetClassIDInfo2`, è necessario verificare che il buffer `typeArgs` sia abbastanza grande per contenere tutti i valori `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="0fcd2-118">After `GetClassIDInfo2` returns, you must verify that the `typeArgs` buffer was large enough to contain all the `ClassID` values.</span></span> <span data-ttu-id="0fcd2-119">A tale scopo, confrontare il valore a cui punta `pcNumTypeArgs` con il valore del parametro `cNumTypeArgs`.</span><span class="sxs-lookup"><span data-stu-id="0fcd2-119">To do this, compare the value that `pcNumTypeArgs` points to with the value of the `cNumTypeArgs` parameter.</span></span> <span data-ttu-id="0fcd2-120">Se `pcNumTypeArgs` punta a un valore maggiore di `cNumTypeArgs`, allocare un buffer `typeArgs` più grande, aggiornare `cNumTypeArgs` con la nuova dimensione e chiamare nuovamente `GetClassIDInfo2`.</span><span class="sxs-lookup"><span data-stu-id="0fcd2-120">If `pcNumTypeArgs` points to a value that is larger than `cNumTypeArgs`, allocate a larger `typeArgs` buffer, update `cNumTypeArgs` with the new, larger size, and call `GetClassIDInfo2` again.</span></span>  
  
 <span data-ttu-id="0fcd2-121">In alternativa, è possibile chiamare innanzitutto `GetClassIDInfo2` con un buffer `typeArgs` di lunghezza zero per ottenere le dimensioni del buffer corrette.</span><span class="sxs-lookup"><span data-stu-id="0fcd2-121">Alternatively, you can first call `GetClassIDInfo2` with a zero-length `typeArgs` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="0fcd2-122">È quindi possibile impostare le dimensioni del buffer `typeArgs` sul valore restituito in `pcNumTypeArgs` e chiamare nuovamente `GetClassIDInfo2`.</span><span class="sxs-lookup"><span data-stu-id="0fcd2-122">You can then set the `typeArgs` buffer size to the value returned in `pcNumTypeArgs` and call `GetClassIDInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fcd2-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0fcd2-123">Requirements</span></span>  
 <span data-ttu-id="0fcd2-124">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fcd2-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fcd2-125">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0fcd2-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0fcd2-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0fcd2-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0fcd2-127">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fcd2-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fcd2-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0fcd2-128">See also</span></span>

- [<span data-ttu-id="0fcd2-129">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="0fcd2-129">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="0fcd2-130">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="0fcd2-130">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
- [<span data-ttu-id="0fcd2-131">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="0fcd2-131">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="0fcd2-132">Profilatura</span><span class="sxs-lookup"><span data-stu-id="0fcd2-132">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)

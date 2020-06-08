---
title: Metodo ICorProfilerInfo2::GetFunctionInfo2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetFunctionInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetFunctionInfo2
helpviewer_keywords:
- GetFunctionInfo2 method [.NET Framework profiling]
- ICorProfilerInfo2::GetFunctionInfo2 method [.NET Framework profiling]
ms.assetid: 0aa60f24-8bbd-4c83-83c5-86ad191b1d82
topic_type:
- apiref
ms.openlocfilehash: f5438ddc655f0f6a7c11d978a47b1bf9e2a13059
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497006"
---
# <a name="icorprofilerinfo2getfunctioninfo2-method"></a><span data-ttu-id="6d4e7-102">Metodo ICorProfilerInfo2::GetFunctionInfo2</span><span class="sxs-lookup"><span data-stu-id="6d4e7-102">ICorProfilerInfo2::GetFunctionInfo2 Method</span></span>
<span data-ttu-id="6d4e7-103">Ottiene la classe padre, il token di metadati e l'elemento `ClassID` di ciascun argomento di tipo, se presente, di una funzione.</span><span class="sxs-lookup"><span data-stu-id="6d4e7-103">Gets the parent class, the metadata token, and the `ClassID` of each type argument, if present, of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d4e7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6d4e7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionInfo2(  
    [in]  FunctionID funcId,  
    [in]  COR_PRF_FRAME_INFO frameInfo,  
    [out] ClassID *pClassId,  
    [out] ModuleID *pModuleId,  
    [out] mdToken *pToken,  
    [in]  ULONG32 cTypeArgs,  
    [out] ULONG32 *pcTypeArgs,  
    [out] ClassID typeArgs[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d4e7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6d4e7-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="6d4e7-106">[in] ID della funzione per cui ottenere la classe padre e altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="6d4e7-106">[in] The ID of the function for which to get the parent class and other information.</span></span>  
  
 `frameInfo`  
 <span data-ttu-id="6d4e7-107">[in] Valore `COR_PRF_FRAME_INFO` che punta alle informazioni su uno stack frame.</span><span class="sxs-lookup"><span data-stu-id="6d4e7-107">[in] A `COR_PRF_FRAME_INFO` value that points to information about a stack frame.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="6d4e7-108">[out] Puntatore alla classe padre della funzione.</span><span class="sxs-lookup"><span data-stu-id="6d4e7-108">[out] A pointer to the parent class of the function.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="6d4e7-109">[out] Puntatore al modulo in cui è definita la classe padre della funzione.</span><span class="sxs-lookup"><span data-stu-id="6d4e7-109">[out] A pointer to the module in which the function's parent class is defined.</span></span>  
  
 `pToken`  
 <span data-ttu-id="6d4e7-110">[out] Puntatore al token di metadati per la funzione.</span><span class="sxs-lookup"><span data-stu-id="6d4e7-110">[out] A pointer to the metadata token for the function.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="6d4e7-111">[in] Dimensione della matrice `typeArgs`.</span><span class="sxs-lookup"><span data-stu-id="6d4e7-111">[in] The size of the `typeArgs` array.</span></span>  
  
 `pcTypeArgs`  
 <span data-ttu-id="6d4e7-112">[out] Puntatore al numero complessivo di valori `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="6d4e7-112">[out] A pointer to the total number of `ClassID` values.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="6d4e7-113">[out] Matrice di valori `ClassID`, ognuno dei quali è l'ID di un argomento tipo della funzione.</span><span class="sxs-lookup"><span data-stu-id="6d4e7-113">[out] An array of `ClassID` values, each of which is the ID of a type argument of the function.</span></span> <span data-ttu-id="6d4e7-114">Dopo il completamento del metodo, `typeArgs` conterrà tutti i valori `ClassID` o alcuni di essi.</span><span class="sxs-lookup"><span data-stu-id="6d4e7-114">When the method returns, `typeArgs` will contain some or all of the `ClassID` values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d4e7-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6d4e7-115">Remarks</span></span>  
 <span data-ttu-id="6d4e7-116">Il codice del profiler può chiamare [ICorProfilerInfo:: GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) per ottenere un'interfaccia di [metadati](../metadata/index.md) per un determinato modulo.</span><span class="sxs-lookup"><span data-stu-id="6d4e7-116">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) to obtain a [metadata](../metadata/index.md) interface for a given module.</span></span> <span data-ttu-id="6d4e7-117">Il token di metadati restituito nella posizione a cui fa riferimento `pToken` può quindi essere usato per accedere ai metadati per la funzione.</span><span class="sxs-lookup"><span data-stu-id="6d4e7-117">The metadata token that is returned to the location referenced by `pToken` can then be used to access the metadata for the function.</span></span>  
  
 <span data-ttu-id="6d4e7-118">L'ID classe e gli argomenti di tipo restituiti tramite i parametri `pClassId` e `typeArgs` dipendono dal valore passato nel parametro `frameInfo`, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="6d4e7-118">The class ID and type arguments that are returned through the `pClassId` and `typeArgs` parameters depend on the value that is passed in the `frameInfo` parameter, as shown in the following table.</span></span>  
  
|<span data-ttu-id="6d4e7-119">Valore del parametro `frameInfo`</span><span class="sxs-lookup"><span data-stu-id="6d4e7-119">Value of the `frameInfo` parameter</span></span>|<span data-ttu-id="6d4e7-120">Risultato</span><span class="sxs-lookup"><span data-stu-id="6d4e7-120">Result</span></span>|  
|----------------------------------------|------------|  
|<span data-ttu-id="6d4e7-121">Valore `COR_PRF_FRAME_INFO` ottenuto da un callback di `FunctionEnter2`</span><span class="sxs-lookup"><span data-stu-id="6d4e7-121">A `COR_PRF_FRAME_INFO` value that was obtained from a `FunctionEnter2` callback</span></span>|<span data-ttu-id="6d4e7-122">L'elemento `ClassID`, restituito nella posizione a cui fa riferimento `pClassId`, e tutti gli argomenti di tipo, restituiti nella matrice `typeArgs`, saranno determinati in modo esatto.</span><span class="sxs-lookup"><span data-stu-id="6d4e7-122">The `ClassID`, returned in the location referenced by `pClassId`, and all type arguments, returned in the `typeArgs` array, will be exact.</span></span>|  
|<span data-ttu-id="6d4e7-123">Valore `COR_PRF_FRAME_INFO` ottenuto da un'origine diversa da un callback di `FunctionEnter2`</span><span class="sxs-lookup"><span data-stu-id="6d4e7-123">A `COR_PRF_FRAME_INFO` that was obtained from a source other than a `FunctionEnter2` callback</span></span>|<span data-ttu-id="6d4e7-124">Non è possibile determinare in modo esatto l'elemento `ClassID` e gli argomenti di tipo.</span><span class="sxs-lookup"><span data-stu-id="6d4e7-124">The exact `ClassID` and type arguments cannot be determined.</span></span> <span data-ttu-id="6d4e7-125">Ciò significa che `ClassID` potrebbe essere null e che alcuni argomenti tipo potrebbero venire restituiti come <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="6d4e7-125">That is, the `ClassID` might be null and some type arguments might come back as <xref:System.Object>.</span></span>|  
|<span data-ttu-id="6d4e7-126">Zero</span><span class="sxs-lookup"><span data-stu-id="6d4e7-126">Zero</span></span>|<span data-ttu-id="6d4e7-127">Non è possibile determinare in modo esatto l'elemento `ClassID` e gli argomenti di tipo.</span><span class="sxs-lookup"><span data-stu-id="6d4e7-127">The exact `ClassID` and type arguments cannot be determined.</span></span> <span data-ttu-id="6d4e7-128">Ciò significa che `ClassID` potrebbe essere null e che alcuni argomenti tipo potrebbero venire restituiti come <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="6d4e7-128">That is, the `ClassID` might be null and some type arguments might come back as <xref:System.Object>.</span></span>|  
  
 <span data-ttu-id="6d4e7-129">Dopo il completamento del metodo `GetFunctionInfo2`, è necessario verificare che il buffer `typeArgs` sia abbastanza grande per contenere tutti i valori `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="6d4e7-129">After `GetFunctionInfo2` returns, you must verify that the `typeArgs` buffer was large enough to contain all the `ClassID` values.</span></span> <span data-ttu-id="6d4e7-130">A tale scopo, confrontare il valore a cui punta `pcTypeArgs` con il valore del parametro `cTypeArgs`.</span><span class="sxs-lookup"><span data-stu-id="6d4e7-130">To do this, compare the value that `pcTypeArgs` points to with the value of the `cTypeArgs` parameter.</span></span> <span data-ttu-id="6d4e7-131">Se `pcTypeArgs` punta a un valore maggiore di `cTypeArgs` diviso per la dimensione di un valore `ClassID`, allocare un buffer `pcTypeArgs` più grande, aggiornare `cTypeArgs` con la nuova dimensione e chiamare nuovamente `GetFunctionInfo2`.</span><span class="sxs-lookup"><span data-stu-id="6d4e7-131">If `pcTypeArgs` points to a value that is larger than `cTypeArgs` divided by the size of a `ClassID` value, allocate a larger `pcTypeArgs` buffer, update `cTypeArgs` with the new, larger size, and call `GetFunctionInfo2` again.</span></span>  
  
 <span data-ttu-id="6d4e7-132">In alternativa, è possibile chiamare innanzitutto `GetFunctionInfo2` con un buffer `pcTypeArgs` di lunghezza zero per ottenere le dimensioni del buffer corrette.</span><span class="sxs-lookup"><span data-stu-id="6d4e7-132">Alternatively, you can first call `GetFunctionInfo2` with a zero-length `pcTypeArgs` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="6d4e7-133">È quindi possibile impostare le dimensioni del buffer sul valore restituito in `pcTypeArgs` diviso per la dimensione di un valore `ClassID` e chiamare di nuovo `GetFunctionInfo2`.</span><span class="sxs-lookup"><span data-stu-id="6d4e7-133">You can then set the buffer size to the value returned in `pcTypeArgs` divided by the size of a `ClassID` value, and call `GetFunctionInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d4e7-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6d4e7-134">Requirements</span></span>  
 <span data-ttu-id="6d4e7-135">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d4e7-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d4e7-136">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6d4e7-136">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6d4e7-137">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d4e7-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d4e7-138">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d4e7-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d4e7-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d4e7-139">See also</span></span>

- [<span data-ttu-id="6d4e7-140">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="6d4e7-140">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="6d4e7-141">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="6d4e7-141">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
- [<span data-ttu-id="6d4e7-142">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="6d4e7-142">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="6d4e7-143">Profilatura</span><span class="sxs-lookup"><span data-stu-id="6d4e7-143">Profiling</span></span>](index.md)

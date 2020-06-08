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
ms.openlocfilehash: a33e51969dc0579d976f08470ebc6e2bcca04dd7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497166"
---
# <a name="icorprofilerinfo2getclassidinfo2-method"></a><span data-ttu-id="3637f-102">Metodo ICorProfilerInfo2::GetClassIDInfo2</span><span class="sxs-lookup"><span data-stu-id="3637f-102">ICorProfilerInfo2::GetClassIDInfo2 Method</span></span>
<span data-ttu-id="3637f-103">Ottiene il modulo padre e il token di metadati per la definizione generica aperta della classe specificata, la proprietà `ClassID` della classe padre e `ClassID` per ogni argomento di tipo, se presente, della classe.</span><span class="sxs-lookup"><span data-stu-id="3637f-103">Gets the parent module and metadata token for the open generic definition of the specified class, the `ClassID` of its parent class, and the `ClassID` for each type argument, if present, of the class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3637f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3637f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassIDInfo2(  
    [in]  ClassID classId,  
    [out] ModuleID *pModuleId,  
    [out] mdTypeDef *pTypeDefToken,  
    [out] ClassID *pParentClassId,  
    [in]  ULONG32 cNumTypeArgs,  
    [out] ULONG32 *pcNumTypeArgs,  
    [out] ClassID typeArgs[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3637f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3637f-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="3637f-106">[in] ID della classe per la quale verranno recuperate le informazioni.</span><span class="sxs-lookup"><span data-stu-id="3637f-106">[in] The ID of the class for which information will be retrieved.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="3637f-107">out Puntatore all'ID del modulo padre per la definizione generica aperta della classe specificata.</span><span class="sxs-lookup"><span data-stu-id="3637f-107">[out] Pointer to the ID of the parent module for the open generic definition of the specified class.</span></span>  
  
 `pTypeDefToken`  
 <span data-ttu-id="3637f-108">out Puntatore al token di metadati per la definizione generica aperta della classe specificata.</span><span class="sxs-lookup"><span data-stu-id="3637f-108">[out] Pointer to the metadata token for the open generic definition of the specified class.</span></span>  
  
 `pParentClassId`  
 <span data-ttu-id="3637f-109">[out] Puntatore all'ID della classe padre.</span><span class="sxs-lookup"><span data-stu-id="3637f-109">[out] Pointer to the ID of the parent class.</span></span>  
  
 `cNumTypeArgs`  
 <span data-ttu-id="3637f-110">[in] Dimensione della matrice `typeArgs`.</span><span class="sxs-lookup"><span data-stu-id="3637f-110">[in] The size of the `typeArgs` array.</span></span>  
  
 `pcNumTypeArgs`  
 <span data-ttu-id="3637f-111">[out] Puntatore al numero complessivo di elementi disponibili.</span><span class="sxs-lookup"><span data-stu-id="3637f-111">[out] Pointer to the total number of available elements.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="3637f-112">[out] Matrice di valori `ClassID`, ognuno dei quali rappresenta l'ID di un argomento di tipo della classe.</span><span class="sxs-lookup"><span data-stu-id="3637f-112">[out] An array of `ClassID` values, each of which represents the ID of a type argument of the class.</span></span> <span data-ttu-id="3637f-113">Quando il metodo restituisce i risultati, `typeArgs` conterrà alcuni o tutti i valori `ClassID` disponibili.</span><span class="sxs-lookup"><span data-stu-id="3637f-113">When the method returns, `typeArgs` will contain some or all the available `ClassID` values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3637f-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3637f-114">Remarks</span></span>  
 <span data-ttu-id="3637f-115">Il `GetClassIDInfo2` metodo è simile al metodo [ICorProfilerInfo:: GetClassIDInfo](icorprofilerinfo-getclassidinfo-method.md) , ma `GetClassIDInfo2` ottiene informazioni aggiuntive su un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="3637f-115">The `GetClassIDInfo2` method is similar to the [ICorProfilerInfo::GetClassIDInfo](icorprofilerinfo-getclassidinfo-method.md) method, but `GetClassIDInfo2` obtains additional information about a generic type.</span></span>  
  
 <span data-ttu-id="3637f-116">Il codice del profiler può chiamare [ICorProfilerInfo:: GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) per ottenere un'interfaccia di [metadati](../metadata/index.md) per un determinato modulo.</span><span class="sxs-lookup"><span data-stu-id="3637f-116">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) to obtain a [metadata](../metadata/index.md) interface for a given module.</span></span> <span data-ttu-id="3637f-117">Il token di metadati restituito al percorso a cui viene fatto riferimento tramite `pTypeDefToken` può quindi essere usato per accedere ai metadati per la classe.</span><span class="sxs-lookup"><span data-stu-id="3637f-117">The metadata token that is returned to the location referenced by `pTypeDefToken` can then be used to access the metadata for the class.</span></span>  
  
 <span data-ttu-id="3637f-118">Dopo il completamento del metodo `GetClassIDInfo2`, è necessario verificare che il buffer `typeArgs` sia abbastanza grande per contenere tutti i valori `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="3637f-118">After `GetClassIDInfo2` returns, you must verify that the `typeArgs` buffer was large enough to contain all the `ClassID` values.</span></span> <span data-ttu-id="3637f-119">A tale scopo, confrontare il valore a cui punta `pcNumTypeArgs` con il valore del parametro `cNumTypeArgs`.</span><span class="sxs-lookup"><span data-stu-id="3637f-119">To do this, compare the value that `pcNumTypeArgs` points to with the value of the `cNumTypeArgs` parameter.</span></span> <span data-ttu-id="3637f-120">Se `pcNumTypeArgs` punta a un valore maggiore di `cNumTypeArgs`, allocare un buffer `typeArgs` più grande, aggiornare `cNumTypeArgs` con la nuova dimensione e chiamare nuovamente `GetClassIDInfo2`.</span><span class="sxs-lookup"><span data-stu-id="3637f-120">If `pcNumTypeArgs` points to a value that is larger than `cNumTypeArgs`, allocate a larger `typeArgs` buffer, update `cNumTypeArgs` with the new, larger size, and call `GetClassIDInfo2` again.</span></span>  
  
 <span data-ttu-id="3637f-121">In alternativa, è possibile chiamare innanzitutto `GetClassIDInfo2` con un buffer `typeArgs` di lunghezza zero per ottenere le dimensioni del buffer corrette.</span><span class="sxs-lookup"><span data-stu-id="3637f-121">Alternatively, you can first call `GetClassIDInfo2` with a zero-length `typeArgs` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="3637f-122">È quindi possibile impostare le dimensioni del buffer `typeArgs` sul valore restituito in `pcNumTypeArgs` e chiamare nuovamente `GetClassIDInfo2`.</span><span class="sxs-lookup"><span data-stu-id="3637f-122">You can then set the `typeArgs` buffer size to the value returned in `pcNumTypeArgs` and call `GetClassIDInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3637f-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3637f-123">Requirements</span></span>  
 <span data-ttu-id="3637f-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3637f-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3637f-125">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3637f-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3637f-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3637f-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3637f-127">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3637f-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3637f-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3637f-128">See also</span></span>

- [<span data-ttu-id="3637f-129">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="3637f-129">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="3637f-130">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="3637f-130">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
- [<span data-ttu-id="3637f-131">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="3637f-131">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="3637f-132">Profilatura</span><span class="sxs-lookup"><span data-stu-id="3637f-132">Profiling</span></span>](index.md)

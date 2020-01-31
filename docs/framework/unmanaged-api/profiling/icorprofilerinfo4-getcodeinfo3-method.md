---
title: Metodo ICorProfilerInfo4::GetCodeInfo3
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetCodeInfo3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetCodeInfo3
helpviewer_keywords:
- GetCodeInfo3 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetCodeInfo3 method [.NET Framework profiling]
ms.assetid: bb8c105e-4d9a-4684-8c05-ed6909cc1b8c
topic_type:
- apiref
ms.openlocfilehash: 164e042ab0f1a275ff07b917658024e22c2d7b0b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862035"
---
# <a name="icorprofilerinfo4getcodeinfo3-method"></a><span data-ttu-id="2729f-102">Metodo ICorProfilerInfo4::GetCodeInfo3</span><span class="sxs-lookup"><span data-stu-id="2729f-102">ICorProfilerInfo4::GetCodeInfo3 Method</span></span>
<span data-ttu-id="2729f-103">Ottiene gli ambiti di codice nativo associati alla versione ricompilata in JIT della funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="2729f-103">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2729f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2729f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodeInfo3(  
    [in]  FunctionID functionID,  
    [in]  ReJITID reJitId,  
    [in]  ULONG32 cCodeInfos,  
    [out] ULONG32 *pcCodeInfos,  
    [out, size_is(cCodeInfos), length_is(*pcCodeInfos)]  
    COR_PRF_CODE_INFO codeInfos[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2729f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2729f-105">Parameters</span></span>  
 `functionID`  
 <span data-ttu-id="2729f-106">[in] ID della funzione alla quale è associato il codice nativo.</span><span class="sxs-lookup"><span data-stu-id="2729f-106">[in] The ID of the function with which the native code is associated.</span></span>  
  
 `reJitId`  
 <span data-ttu-id="2729f-107">[in] Identità della funzione ricompilata in JIT.</span><span class="sxs-lookup"><span data-stu-id="2729f-107">[in] The identity of the JIT-recompiled function.</span></span>  
  
 `cCodeInfos`  
 <span data-ttu-id="2729f-108">[in] Dimensione della matrice `codeInfos`.</span><span class="sxs-lookup"><span data-stu-id="2729f-108">[in] The size of the `codeInfos` array.</span></span>  
  
 `pcCodeInfos`  
 <span data-ttu-id="2729f-109">out Puntatore al numero totale di strutture di [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) disponibili.</span><span class="sxs-lookup"><span data-stu-id="2729f-109">[out] A pointer to the total number of [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structures available.</span></span>  
  
 `codeInfos`  
 <span data-ttu-id="2729f-110">[out] Buffer fornito dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="2729f-110">[out] A caller-provided buffer.</span></span> <span data-ttu-id="2729f-111">Una volta completato, il metodo contiene una matrice di strutture `COR_PRF_CODE_INFO`, ognuna delle quali descrive un blocco di codice nativo.</span><span class="sxs-lookup"><span data-stu-id="2729f-111">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2729f-112">Note</span><span class="sxs-lookup"><span data-stu-id="2729f-112">Remarks</span></span>  
 <span data-ttu-id="2729f-113">Il `GetCodeInfo3` metodo è simile a [GetCodeInfo2](icorprofilerinfo2-getcodeinfo2-method.md), ad eccezione del fatto che otterrà l'ID ricompilata in JIT della funzione che contiene l'indirizzo IP specificato.</span><span class="sxs-lookup"><span data-stu-id="2729f-113">The `GetCodeInfo3` method is similar to [GetCodeInfo2](icorprofilerinfo2-getcodeinfo2-method.md), except that it will get the JIT-recompiled ID of the function that contains the specified IP address.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2729f-114">`GetCodeInfo3` possibile attivare un Garbage Collection, mentre [GetCodeInfo2](icorprofilerinfo2-getcodeinfo2-method.md) non lo è.</span><span class="sxs-lookup"><span data-stu-id="2729f-114">`GetCodeInfo3` can trigger a garbage collection, whereas [GetCodeInfo2](icorprofilerinfo2-getcodeinfo2-method.md) will not.</span></span> <span data-ttu-id="2729f-115">Per ulteriori informazioni, vedere il [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](corprof-e-unsupported-call-sequence-hresult.md) HRESULT.</span><span class="sxs-lookup"><span data-stu-id="2729f-115">For more information, see the [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](corprof-e-unsupported-call-sequence-hresult.md) HRESULT.</span></span>  
  
 <span data-ttu-id="2729f-116">Gli ambiti vengono ordinati in sequenza crescente in base all'offset CIL (Common Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="2729f-116">The extents are sorted in order of increasing Common Intermediate Language (CIL) offset.</span></span>  
  
 <span data-ttu-id="2729f-117">Quando `GetCodeInfo3` restituisce, è necessario verificare che il buffer di `codeInfos` sia sufficientemente grande da contenere tutte le strutture di [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="2729f-117">After `GetCodeInfo3` returns, you must verify that the `codeInfos` buffer was large enough to contain all the [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structures.</span></span> <span data-ttu-id="2729f-118">A tale scopo, confrontare il valore di `cCodeInfos` con il valore del parametro `cchName`.</span><span class="sxs-lookup"><span data-stu-id="2729f-118">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="2729f-119">Se `cCodeInfos` diviso per la dimensione di una struttura [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) è inferiore a `pcCodeInfos`, allocare un `codeInfos` buffer più grande, aggiornare `cCodeInfos` con la nuova dimensione maggiore e chiamare `GetCodeInfo3` di nuovo.</span><span class="sxs-lookup"><span data-stu-id="2729f-119">If `cCodeInfos` divided by the size of a [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo3` again.</span></span>  
  
 <span data-ttu-id="2729f-120">In alternativa, è possibile chiamare innanzitutto `GetCodeInfo3` con un buffer `codeInfos` di lunghezza zero per ottenere le dimensioni del buffer corrette.</span><span class="sxs-lookup"><span data-stu-id="2729f-120">Alternatively, you can first call `GetCodeInfo3` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="2729f-121">È quindi possibile impostare le dimensioni del buffer `codeInfos` sul valore restituito in `pcCodeInfos`, moltiplicato per la dimensione di una struttura [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) e chiamare nuovamente `GetCodeInfo3`.</span><span class="sxs-lookup"><span data-stu-id="2729f-121">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structure, and call `GetCodeInfo3` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2729f-122">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="2729f-122">Requirements</span></span>  
 <span data-ttu-id="2729f-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2729f-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2729f-124">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2729f-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2729f-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2729f-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2729f-126">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2729f-126">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2729f-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2729f-127">See also</span></span>

- [<span data-ttu-id="2729f-128">Metodo GetCodeInfo2</span><span class="sxs-lookup"><span data-stu-id="2729f-128">GetCodeInfo2 Method</span></span>](icorprofilerinfo2-getcodeinfo2-method.md)
- [<span data-ttu-id="2729f-129">Interfaccia ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="2729f-129">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="2729f-130">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="2729f-130">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="2729f-131">Profilatura</span><span class="sxs-lookup"><span data-stu-id="2729f-131">Profiling</span></span>](index.md)

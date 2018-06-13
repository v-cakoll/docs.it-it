---
title: Metodo ICorProfilerInfo2::GetCodeInfo2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetCodeInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetCodeInfo2
helpviewer_keywords:
- ICorProfilerInfo2::GetCodeInfo2 method [.NET Framework profiling]
- GetCodeInfo2 method [.NET Framework profiling]
ms.assetid: 532da6ee-7f0a-401b-a61e-fc47ec235d2e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b7db9b5af9b8bb8419573ef90ddf8beef697cb5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457500"
---
# <a name="icorprofilerinfo2getcodeinfo2-method"></a><span data-ttu-id="cf0dc-102">Metodo ICorProfilerInfo2::GetCodeInfo2</span><span class="sxs-lookup"><span data-stu-id="cf0dc-102">ICorProfilerInfo2::GetCodeInfo2 Method</span></span>
<span data-ttu-id="cf0dc-103">Ottiene gli ambiti del codice nativo associato al parametro `FunctionID` specificato.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-103">Gets the extents of native code associated with the specified `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf0dc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cf0dc-104">Syntax</span></span>  
  
```  
HRESULT GetCodeInfo2(  
    [in]  FunctionID functionID,  
    [in]  ULONG32 cCodeInfos,  
    [out] ULONG32 *pcCodeInfos,  
    [out, size_is(cCodeInfos), length_is(*pcCodeInfos)]  
    COR_PRF_CODE_INFO codeInfos[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cf0dc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cf0dc-105">Parameters</span></span>  
 `functionID`  
 <span data-ttu-id="cf0dc-106">[in] ID della funzione alla quale è associato il codice nativo.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-106">[in] The ID of the function with which the native code is associated.</span></span>  
  
 `cCodeInfos`  
 <span data-ttu-id="cf0dc-107">[in] Dimensione della matrice `codeInfos`.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-107">[in] The size of the `codeInfos` array.</span></span>  
  
 `pcCodeInfos`  
 <span data-ttu-id="cf0dc-108">[out] Un puntatore al numero totale di [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) strutture disponibili.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-108">[out] A pointer to the total number of [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures available.</span></span>  
  
 `codeInfos`  
 <span data-ttu-id="cf0dc-109">[out] Buffer fornito dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-109">[out] A caller-provided buffer.</span></span> <span data-ttu-id="cf0dc-110">Una volta completato, il metodo contiene una matrice di strutture `COR_PRF_CODE_INFO`, ognuna delle quali descrive un blocco di codice nativo.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-110">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf0dc-111">Note</span><span class="sxs-lookup"><span data-stu-id="cf0dc-111">Remarks</span></span>  
 <span data-ttu-id="cf0dc-112">Gli ambiti vengono ordinati in sequenza crescente in base all'offset MSIL (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="cf0dc-112">The extents are sorted in order of increasing Microsoft intermediate language (MSIL) offset.</span></span>  
  
 <span data-ttu-id="cf0dc-113">Dopo il completamento del metodo `GetCodeInfo2`, è necessario verificare che il buffer `codeInfos` sia abbastanza grande per contenere tutte le strutture `COR_PRF_CODE_INFO`.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-113">After `GetCodeInfo2` returns, you must verify that the `codeInfos` buffer was large enough to contain all the `COR_PRF_CODE_INFO` structures.</span></span> <span data-ttu-id="cf0dc-114">A tale scopo, confrontare il valore di `cCodeInfos` con il valore del parametro `cchName`.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-114">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="cf0dc-115">Se il valore `cCodeInfos`, diviso per la dimensione di una struttura `COR_PRF_CODE_INFO`, è inferiore a `pcCodeInfos`, allocare un buffer `codeInfos` più grande, aggiornare `cCodeInfos` con la nuova dimensione e chiamare nuovamente `GetCodeInfo2`.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-115">If `cCodeInfos` divided by the size of a `COR_PRF_CODE_INFO` structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo2` again.</span></span>  
  
 <span data-ttu-id="cf0dc-116">In alternativa, è possibile chiamare innanzitutto `GetCodeInfo2` con un buffer `codeInfos` di lunghezza zero per ottenere le dimensioni del buffer corrette.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-116">Alternatively, you can first call `GetCodeInfo2` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="cf0dc-117">È quindi possibile impostare le dimensioni del buffer `codeInfos` sul valore restituito in `pcCodeInfos` moltiplicato per la dimensione di una struttura `COR_PRF_CODE_INFO` e chiamare di nuovo `GetCodeInfo2`.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-117">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a `COR_PRF_CODE_INFO` structure, and call `GetCodeInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf0dc-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cf0dc-118">Requirements</span></span>  
 <span data-ttu-id="cf0dc-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf0dc-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf0dc-120">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cf0dc-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cf0dc-121">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="cf0dc-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf0dc-122">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf0dc-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf0dc-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf0dc-123">See Also</span></span>  
 [<span data-ttu-id="cf0dc-124">Metodo GetCodeInfo3</span><span class="sxs-lookup"><span data-stu-id="cf0dc-124">GetCodeInfo3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md)  
 [<span data-ttu-id="cf0dc-125">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="cf0dc-125">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 [<span data-ttu-id="cf0dc-126">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="cf0dc-126">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="cf0dc-127">Profilatura</span><span class="sxs-lookup"><span data-stu-id="cf0dc-127">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)

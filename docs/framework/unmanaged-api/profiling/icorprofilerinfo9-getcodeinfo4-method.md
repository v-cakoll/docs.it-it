---
title: ICorProfilerInfo9::GetCodeInfo4
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetCodeInfo4
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: ce29703a181106353695414e8b291b14c697fc56
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444793"
---
# <a name="icorprofilerinfo9getcodeinfo4-method"></a><span data-ttu-id="b65af-102">Metodo ICorProfilerInfo9:: GetCodeInfo4</span><span class="sxs-lookup"><span data-stu-id="b65af-102">ICorProfilerInfo9::GetCodeInfo4 Method</span></span>

<span data-ttu-id="b65af-103">Dato l'indirizzo iniziale del codice nativo, restituisce i blocchi di memoria virtuale che archiviano il codice.</span><span class="sxs-lookup"><span data-stu-id="b65af-103">Given the native code start address, returns the blocks of virtual memory that store this code.</span></span>

## <a name="syntax"></a><span data-ttu-id="b65af-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b65af-104">Syntax</span></span>

```cpp
HRESULT GetCodeInfo4( [in]  UINT_PTR pNativeCodeStartAddress,
                      [in]  ULONG32 cCodeInfos,
                      [out] ULONG32* pcCodeInfos,
                      [out] COR_PRF_CODE_INFO codeInfos[]);
```

#### <a name="parameters"></a><span data-ttu-id="b65af-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b65af-105">Parameters</span></span>

`pNativeCodeStartAddress` \
<span data-ttu-id="b65af-106">in Puntatore all'inizio di una funzione nativa.</span><span class="sxs-lookup"><span data-stu-id="b65af-106">[in] A pointer to the start of a native function.</span></span>

`cCodeInfos` \
<span data-ttu-id="b65af-107">[in] Dimensione della matrice `codeInfos`.</span><span class="sxs-lookup"><span data-stu-id="b65af-107">[in] The size of the `codeInfos` array.</span></span>

`pcCodeInfos` \
<span data-ttu-id="b65af-108">out Puntatore al numero totale di strutture di [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) disponibili.</span><span class="sxs-lookup"><span data-stu-id="b65af-108">[out] A pointer to the total number of [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures available.</span></span>

`codeInfos` \
<span data-ttu-id="b65af-109">[out] Buffer fornito dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="b65af-109">[out] A caller-provided buffer.</span></span> <span data-ttu-id="b65af-110">Una volta completato, il metodo contiene una matrice di strutture `COR_PRF_CODE_INFO`, ognuna delle quali descrive un blocco di codice nativo.</span><span class="sxs-lookup"><span data-stu-id="b65af-110">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>

## <a name="remarks"></a><span data-ttu-id="b65af-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b65af-111">Remarks</span></span>

<span data-ttu-id="b65af-112">Il `GetCodeInfo4` metodo è simile a [GetCodeInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md), con la differenza che è possibile cercare informazioni sul codice per versioni native diverse di un metodo.</span><span class="sxs-lookup"><span data-stu-id="b65af-112">The `GetCodeInfo4` method is similar to [GetCodeInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md), except that it can look up code information for different native versions of a method.</span></span>

> [!NOTE]
> <span data-ttu-id="b65af-113">`GetCodeInfo4` possibile attivare una Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b65af-113">`GetCodeInfo4` can trigger a garbage collection.</span></span>

<span data-ttu-id="b65af-114">Gli ambiti vengono ordinati in sequenza crescente in base all'offset CIL (Common Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="b65af-114">The extents are sorted in order of increasing Common Intermediate Language (CIL) offset.</span></span>

<span data-ttu-id="b65af-115">Quando `GetCodeInfo4` restituisce, è necessario verificare che il buffer di `codeInfos` sia sufficientemente grande da contenere tutte le strutture di [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="b65af-115">After `GetCodeInfo4` returns, you must verify that the `codeInfos` buffer was large enough to contain all the [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures.</span></span> <span data-ttu-id="b65af-116">A tale scopo, confrontare il valore di `cCodeInfos` con il valore del parametro `cchName`.</span><span class="sxs-lookup"><span data-stu-id="b65af-116">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="b65af-117">Se `cCodeInfos` diviso per la dimensione di una struttura di [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) è inferiore `pcCodeInfos`, allocare un buffer di `codeInfos` più grande, aggiornare `cCodeInfos` con la nuova dimensione maggiore e chiamare di nuovo `GetCodeInfo4`.</span><span class="sxs-lookup"><span data-stu-id="b65af-117">If `cCodeInfos` divided by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo4` again.</span></span>

<span data-ttu-id="b65af-118">In alternativa, è possibile chiamare innanzitutto `GetCodeInfo4` con un buffer `codeInfos` di lunghezza zero per ottenere le dimensioni del buffer corrette.</span><span class="sxs-lookup"><span data-stu-id="b65af-118">Alternatively, you can first call `GetCodeInfo4` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="b65af-119">È quindi possibile impostare le dimensioni del buffer `codeInfos` sul valore restituito in `pcCodeInfos`, moltiplicato per la dimensione di una struttura [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) e chiamare nuovamente `GetCodeInfo4`.</span><span class="sxs-lookup"><span data-stu-id="b65af-119">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure, and call `GetCodeInfo4` again.</span></span>

## <a name="requirements"></a><span data-ttu-id="b65af-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b65af-120">Requirements</span></span>

<span data-ttu-id="b65af-121">**Piattaforme:** Vedere [sistemi operativi supportati da .NET Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="b65af-121">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="b65af-122">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b65af-122">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="b65af-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b65af-123">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="b65af-124">**Versioni di .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b65af-124">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b65af-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b65af-125">See also</span></span>

- [<span data-ttu-id="b65af-126">Interfaccia ICorProfilerInfo9</span><span class="sxs-lookup"><span data-stu-id="b65af-126">ICorProfilerInfo9 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/ICorProfilerInfo9-interface.md)

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
ms.openlocfilehash: e0493ed3f8796019d5715ef468c88675b9970a39
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973841"
---
# <a name="icorprofilerinfo9getcodeinfo4-method"></a><span data-ttu-id="8cb8c-102">Metodo ICorProfilerInfo9:: GetCodeInfo4</span><span class="sxs-lookup"><span data-stu-id="8cb8c-102">ICorProfilerInfo9::GetCodeInfo4 Method</span></span>
  
 <span data-ttu-id="8cb8c-103">Dato l'indirizzo iniziale del codice nativo, restituisce i blocchi di memoria virtuale che archiviano il codice.</span><span class="sxs-lookup"><span data-stu-id="8cb8c-103">Given the native code start address, returns the blocks of virtual memory that store this code.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="8cb8c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8cb8c-104">Syntax</span></span>  
  
```cpp
HRESULT GetCodeInfo4( [in]  UINT_PTR pNativeCodeStartAddress,
                      [in]  ULONG32 cCodeInfos,
                      [out] ULONG32* pcCodeInfos,
                      [out] COR_PRF_CODE_INFO codeInfos[]);
```  
  
#### <a name="parameters"></a><span data-ttu-id="8cb8c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8cb8c-105">Parameters</span></span>  
 `pNativeCodeStartAddress`  
 <span data-ttu-id="8cb8c-106">in Puntatore all'inizio di una funzione nativa.</span><span class="sxs-lookup"><span data-stu-id="8cb8c-106">[in] A pointer to the start of a native function.</span></span>  

 `cCodeInfos`  
 <span data-ttu-id="8cb8c-107">[in] Dimensione della matrice `codeInfos`.</span><span class="sxs-lookup"><span data-stu-id="8cb8c-107">[in] The size of the `codeInfos` array.</span></span>  
  
 `pcCodeInfos`  
 <span data-ttu-id="8cb8c-108">out Puntatore al numero totale di strutture [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) disponibili.</span><span class="sxs-lookup"><span data-stu-id="8cb8c-108">[out] A pointer to the total number of [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures available.</span></span>  
  
 `codeInfos`  
 <span data-ttu-id="8cb8c-109">[out] Buffer fornito dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="8cb8c-109">[out] A caller-provided buffer.</span></span> <span data-ttu-id="8cb8c-110">Una volta completato, il metodo contiene una matrice di strutture `COR_PRF_CODE_INFO`, ognuna delle quali descrive un blocco di codice nativo.</span><span class="sxs-lookup"><span data-stu-id="8cb8c-110">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8cb8c-111">Note</span><span class="sxs-lookup"><span data-stu-id="8cb8c-111">Remarks</span></span>  
 <span data-ttu-id="8cb8c-112">Il `GetCodeInfo4` metodo è simile a [GetCodeInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md), ad eccezione del fatto che può cercare informazioni sul codice per versioni native diverse di un metodo.</span><span class="sxs-lookup"><span data-stu-id="8cb8c-112">The `GetCodeInfo4` method is similar to [GetCodeInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md), except that it can look up code information for different native versions of a method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8cb8c-113">`GetCodeInfo4`può attivare un Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="8cb8c-113">`GetCodeInfo4` can trigger a garbage collection.</span></span>
  
 <span data-ttu-id="8cb8c-114">Gli ambiti vengono ordinati in sequenza crescente in base all'offset CIL (Common Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="8cb8c-114">The extents are sorted in order of increasing Common Intermediate Language (CIL) offset.</span></span>  
  
 <span data-ttu-id="8cb8c-115">Dopo `GetCodeInfo4` la restituzione di, è necessario `codeInfos` verificare che il buffer sia abbastanza grande per contenere tutte le strutture [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="8cb8c-115">After `GetCodeInfo4` returns, you must verify that the `codeInfos` buffer was large enough to contain all the [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures.</span></span> <span data-ttu-id="8cb8c-116">A tale scopo, confrontare il valore di `cCodeInfos` con il valore del parametro `cchName`.</span><span class="sxs-lookup"><span data-stu-id="8cb8c-116">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="8cb8c-117">Se `cCodeInfos` diviso per la dimensione di una struttura [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) è inferiore a `pcCodeInfos`, allocare un `codeInfos` buffer più grande, aggiornare `cCodeInfos` con la nuova dimensione maggiore e chiamare `GetCodeInfo4` di nuovo.</span><span class="sxs-lookup"><span data-stu-id="8cb8c-117">If `cCodeInfos` divided by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo4` again.</span></span>  
  
 <span data-ttu-id="8cb8c-118">In alternativa, è possibile chiamare innanzitutto `GetCodeInfo4` con un buffer `codeInfos` di lunghezza zero per ottenere le dimensioni del buffer corrette.</span><span class="sxs-lookup"><span data-stu-id="8cb8c-118">Alternatively, you can first call `GetCodeInfo4` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="8cb8c-119">È quindi possibile impostare le `codeInfos` dimensioni del buffer sul valore restituito in `pcCodeInfos`, moltiplicato per la dimensione di una struttura [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) e chiamare `GetCodeInfo4` di nuovo.</span><span class="sxs-lookup"><span data-stu-id="8cb8c-119">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure, and call `GetCodeInfo4` again.</span></span>   
  

## <a name="requirements"></a><span data-ttu-id="8cb8c-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8cb8c-120">Requirements</span></span>  
 <span data-ttu-id="8cb8c-121">**Piattaforme** Vedere [sistemi operativi supportati da .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="8cb8c-121">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
  
 <span data-ttu-id="8cb8c-122">**Intestazione:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="8cb8c-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8cb8c-123">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8cb8c-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8cb8c-124">**Versioni di .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cb8c-124">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8cb8c-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8cb8c-125">See also</span></span>
- [<span data-ttu-id="8cb8c-126">Interfaccia ICorProfilerInfo9</span><span class="sxs-lookup"><span data-stu-id="8cb8c-126">ICorProfilerInfo9 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/ICorProfilerInfo9-interface.md)


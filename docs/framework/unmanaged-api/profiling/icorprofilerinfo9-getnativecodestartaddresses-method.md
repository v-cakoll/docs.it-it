---
title: ICorProfilerInfo9::GetNativeCodeStartAddresses
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetNativeCodeStartAddresses
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 7593e8873c2714df85146903c0052a9909a95ccd
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444724"
---
# <a name="icorprofilerinfo9getnativecodestartaddresses-method"></a><span data-ttu-id="d9657-102">Metodo ICorProfilerInfo9:: GetNativeCodeStartAddresses</span><span class="sxs-lookup"><span data-stu-id="d9657-102">ICorProfilerInfo9::GetNativeCodeStartAddresses Method</span></span>

<span data-ttu-id="d9657-103">Dato un functionId e rejitId, enumera l'indirizzo iniziale del codice nativo di tutte le versioni compilato JIT del codice attualmente esistente.</span><span class="sxs-lookup"><span data-stu-id="d9657-103">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span>

## <a name="syntax"></a><span data-ttu-id="d9657-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d9657-104">Syntax</span></span>

```cpp
HRESULT GetNativeCodeStartAddresses( [in]  FunctionID functionID,
                                     [in]  ReJITID reJitId,
                                     [in]  ULONG32 cCodeStartAddresses,
                                     [out] ULONG32 *pcCodeStartAddresses,
                                     [out] UINT_PTR codeStartAddresses[]);
```

#### <a name="parameters"></a><span data-ttu-id="d9657-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d9657-105">Parameters</span></span>

`functionId` \
<span data-ttu-id="d9657-106">in ID della funzione i cui indirizzi di avvio del codice nativo devono essere restituiti.</span><span class="sxs-lookup"><span data-stu-id="d9657-106">[in] The ID of the function whose native code start addresses should be returned.</span></span>

`reJitId` \
<span data-ttu-id="d9657-107">[in] Identità della funzione ricompilata in JIT.</span><span class="sxs-lookup"><span data-stu-id="d9657-107">[in] The identity of the JIT-recompiled function.</span></span>

`cCodeStartAddresses` \
<span data-ttu-id="d9657-108">[in] Dimensione massima della matrice `codeStartAddresses`.</span><span class="sxs-lookup"><span data-stu-id="d9657-108">[in] The maximum size of the `codeStartAddresses` array.</span></span>

`pcCodeStartAddresses` \
<span data-ttu-id="d9657-109">out Numero di indirizzi disponibili.</span><span class="sxs-lookup"><span data-stu-id="d9657-109">[out] The number of available addresses.</span></span>

`codeStartAddresses` \
<span data-ttu-id="d9657-110">out Matrice di `UINT_PTR`, ciascuno dei quali è l'indirizzo iniziale per un corpo nativo per la funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="d9657-110">[out] An array of `UINT_PTR`, each one of which is the start address for a native body for the specified function.</span></span>

## <a name="remarks"></a><span data-ttu-id="d9657-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d9657-111">Remarks</span></span>

<span data-ttu-id="d9657-112">Quando è abilitata la compilazione a più livelli, una funzione può avere più di un corpo del codice nativo.</span><span class="sxs-lookup"><span data-stu-id="d9657-112">When tiered compilation is enabled, a function may have more than one native code body.</span></span>

## <a name="requirements"></a><span data-ttu-id="d9657-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d9657-113">Requirements</span></span>

<span data-ttu-id="d9657-114">**Piattaforme:** Vedere [sistemi operativi supportati da .NET Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="d9657-114">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="d9657-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d9657-115">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="d9657-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9657-116">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="d9657-117">**Versioni di .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9657-117">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d9657-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9657-118">See also</span></span>

- [<span data-ttu-id="d9657-119">Interfaccia ICorProfilerInfo9</span><span class="sxs-lookup"><span data-stu-id="d9657-119">ICorProfilerInfo9 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md)

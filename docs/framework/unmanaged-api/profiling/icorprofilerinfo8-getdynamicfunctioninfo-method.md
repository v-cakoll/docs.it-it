---
title: ICorProfilerInfo8::GetDynamicFunctionInfo
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.GetDynamicFunctionInfo
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: eaf33f3b0de7a18e400cd16d29c046784e2e190f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495320"
---
# <a name="icorprofilerinfo8getdynamicfunctioninfo-method"></a><span data-ttu-id="bade5-102">Metodo ICorProfilerInfo8:: GetDynamicFunctionInfo</span><span class="sxs-lookup"><span data-stu-id="bade5-102">ICorProfilerInfo8::GetDynamicFunctionInfo Method</span></span>

<span data-ttu-id="bade5-103">Recupera informazioni sui metodi dinamici.</span><span class="sxs-lookup"><span data-stu-id="bade5-103">Retrieves information about dynamic methods.</span></span>

## <a name="syntax"></a><span data-ttu-id="bade5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bade5-104">Syntax</span></span>

```cpp
HRESULT GetDynamicFunctionInfo( [in]  FunctionID              functionId,
                                [out] ModuleID                *moduleId,
                                [out] PCCOR_SIGNATURE         *ppvSig,
                                [out] ULONG                   *pbSig,
                                [in]  ULONG                   cchName,
                                [out] ULONG                   *pcchName,
                                [out] WCHAR                   wszName[]);
```

## <a name="parameters"></a><span data-ttu-id="bade5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bade5-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="bade5-106">\[in] ID della funzione per la quale recuperare le informazioni.</span><span class="sxs-lookup"><span data-stu-id="bade5-106">\[in] The ID of the function for which to retrieve information.</span></span>

- `moduleId`

  <span data-ttu-id="bade5-107">\[in] puntatore al modulo in cui è definita la classe padre della funzione.</span><span class="sxs-lookup"><span data-stu-id="bade5-107">\[in] A pointer to the module in which the function's parent class is defined.</span></span>

- `ppvSig`

  <span data-ttu-id="bade5-108">\[out] puntatore alla firma della funzione.</span><span class="sxs-lookup"><span data-stu-id="bade5-108">\[out] A pointer to the signature for the function.</span></span>

- `pbSig`

  <span data-ttu-id="bade5-109">\[out] puntatore al numero di byte per la firma della funzione.</span><span class="sxs-lookup"><span data-stu-id="bade5-109">\[out] A pointer to the count of bytes for the function signature.</span></span>

- `cchName`

  <span data-ttu-id="bade5-110">\[in] dimensione massima della `wszName` matrice.</span><span class="sxs-lookup"><span data-stu-id="bade5-110">\[in] The maximum size of the `wszName` array.</span></span>

- `pcchName`

  <span data-ttu-id="bade5-111">\[out] numero di caratteri nella `wszName` matrice.</span><span class="sxs-lookup"><span data-stu-id="bade5-111">\[out] The number of characters in the `wszName` array.</span></span>

- `wszName`

  <span data-ttu-id="bade5-112">\[out] matrice di `WCHAR` che rappresenta il nome della funzione, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="bade5-112">\[out] An array of `WCHAR` which is the name of the function, if one exists.</span></span>

## <a name="remarks"></a><span data-ttu-id="bade5-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="bade5-113">Remarks</span></span>

<span data-ttu-id="bade5-114">Alcuni metodi come gli stub IL o LCG non dispongono di metadati associati che possono essere recuperati tramite le API [IMetaDataImport](../metadata/imetadataimport-interface.md) e [IMetaDataImport2](../metadata/imetadataimport2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="bade5-114">Certain methods like IL Stubs or LCG do not have associated metadata that can be retrieved using the [IMetaDataImport](../metadata/imetadataimport-interface.md) and [IMetaDataImport2](../metadata/imetadataimport2-interface.md) APIs.</span></span> <span data-ttu-id="bade5-115">Questi metodi possono essere rilevati dai profiler tramite i puntatori all'istruzione oppure ascoltando [ICorProfilerCallback8::D ynamicmethodjitcompilationstarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span><span class="sxs-lookup"><span data-stu-id="bade5-115">Such methods can be encountered by profilers through instruction pointers or by listening to [ICorProfilerCallback8::DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span></span>

<span data-ttu-id="bade5-116">Questa API può essere usata per recuperare informazioni sui metodi dinamici, incluso un nome descrittivo, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="bade5-116">This API can be used to retrieve information about dynamic methods, including a friendly name, if available.</span></span>

## <a name="requirements"></a><span data-ttu-id="bade5-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bade5-117">Requirements</span></span>

<span data-ttu-id="bade5-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bade5-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="bade5-119">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bade5-119">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="bade5-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bade5-120">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="bade5-121">**Versioni .NET Framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bade5-121">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="bade5-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bade5-122">See also</span></span>

- [<span data-ttu-id="bade5-123">Interfaccia ICorProfilerInfo8</span><span class="sxs-lookup"><span data-stu-id="bade5-123">ICorProfilerInfo8 Interface</span></span>](icorprofilerinfo8-interface.md)

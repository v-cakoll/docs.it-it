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
ms.openlocfilehash: 90246ade67f797c04f0da5d9a68dadb83e4ce418
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973861"
---
# <a name="icorprofilerinfo8getdynamicfunctioninfo-method"></a><span data-ttu-id="082fd-102">Metodo ICorProfilerInfo8:: GetDynamicFunctionInfo</span><span class="sxs-lookup"><span data-stu-id="082fd-102">ICorProfilerInfo8::GetDynamicFunctionInfo Method</span></span>
  
 <span data-ttu-id="082fd-103">Recupera informazioni sui metodi dinamici.</span><span class="sxs-lookup"><span data-stu-id="082fd-103">Retrieves information about dynamic methods.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="082fd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="082fd-104">Syntax</span></span>  
  
```cpp
HRESULT GetDynamicFunctionInfo( [in]  FunctionID              functionId,
                                [out] ModuleID                *moduleId,
                                [out] PCCOR_SIGNATURE         *ppvSig,
                                [out] ULONG                   *pbSig,
                                [in]  ULONG                   cchName,
                                [out] ULONG                   *pcchName,
                                [out] WCHAR                   wszName[]);
```  
  
#### <a name="parameters"></a><span data-ttu-id="082fd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="082fd-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="082fd-106">in ID della funzione per la quale recuperare le informazioni.</span><span class="sxs-lookup"><span data-stu-id="082fd-106">[in] The ID of the function for which to retrieve information.</span></span>  

 `moduleId`  
 <span data-ttu-id="082fd-107">in Puntatore al modulo in cui è definita la classe padre della funzione.</span><span class="sxs-lookup"><span data-stu-id="082fd-107">[in] A pointer to the module in which the function's parent class is defined.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="082fd-108">out Puntatore alla firma della funzione.</span><span class="sxs-lookup"><span data-stu-id="082fd-108">[out] A pointer to the signature for the function.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="082fd-109">out Puntatore al numero di byte per la firma della funzione.</span><span class="sxs-lookup"><span data-stu-id="082fd-109">[out] A pointer to the count of bytes for the function signature.</span></span>
  
 `cchName`  
 <span data-ttu-id="082fd-110">[in] Dimensione massima della matrice `wszName`.</span><span class="sxs-lookup"><span data-stu-id="082fd-110">[in] The maximum size of the `wszName` array.</span></span>
  
 `pcchName`  
 <span data-ttu-id="082fd-111">out Numero di caratteri nella `wszName` matrice.</span><span class="sxs-lookup"><span data-stu-id="082fd-111">[out] The number of characters in the `wszName` array.</span></span>

 `wszName` \
 <span data-ttu-id="082fd-112">out Matrice di `WCHAR` che rappresenta il nome della funzione, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="082fd-112">[out] An array of `WCHAR` which is the name of the function, if one exists.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="082fd-113">Note</span><span class="sxs-lookup"><span data-stu-id="082fd-113">Remarks</span></span>  
 <span data-ttu-id="082fd-114">Alcuni metodi come gli stub IL o LCG non dispongono di metadati associati che possono essere recuperati tramite le API [IMetaDataImport](../metadata/imetadataimport-interface.md) e [IMetaDataImport2](../metadata/imetadataimport2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="082fd-114">Certain methods like IL Stubs or LCG do not have associated metadata that can be retrieved using the [IMetaDataImport](../metadata/imetadataimport-interface.md) and [IMetaDataImport2](../metadata/imetadataimport2-interface.md) APIs.</span></span> <span data-ttu-id="082fd-115">Questi metodi possono essere rilevati dai profiler tramite i puntatori all'istruzione oppure ascoltando [ICorProfilerCallback8::D ynamicmethodjitcompilationstarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span><span class="sxs-lookup"><span data-stu-id="082fd-115">Such methods can be encountered by profilers through instruction pointers or by listening to [ICorProfilerCallback8::DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span></span>

 <span data-ttu-id="082fd-116">Questa API può essere usata per recuperare informazioni sui metodi dinamici, incluso un nome descrittivo, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="082fd-116">This API can be used to retrieve information about dynamic methods, including a friendly name, if available.</span></span>  
  

## <a name="requirements"></a><span data-ttu-id="082fd-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="082fd-117">Requirements</span></span>  
 <span data-ttu-id="082fd-118">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="082fd-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="082fd-119">**Intestazione:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="082fd-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="082fd-120">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="082fd-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="082fd-121">**Versioni .NET Framework:** [! INCLUDi[net_current_v472plus](../../../../includes/net-current-v472plus.md)</span><span class="sxs-lookup"><span data-stu-id="082fd-121">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="082fd-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="082fd-122">See also</span></span>
- [<span data-ttu-id="082fd-123">Interfaccia ICorProfilerInfo8</span><span class="sxs-lookup"><span data-stu-id="082fd-123">ICorProfilerInfo8 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)


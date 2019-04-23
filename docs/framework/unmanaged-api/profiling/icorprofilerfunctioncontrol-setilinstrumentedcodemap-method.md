---
title: Metodo ICorProfilerFunctionControl::SetILInstrumentedCodeMap
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetILInstrumentedCodeMap
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetILInstrumentedCodeMap
helpviewer_keywords:
- ICorProfilerFunctionControl::SetILInstrumentedCodeMap method [.NET Framework profiling]
- SetIILInstrumentedCodeMap method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: ecf56646-7e5f-46c4-8340-f3a04e88920f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b36439dd6fb882bb41c38e953cb7b1c5f2b93d30
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59074105"
---
# <a name="icorprofilerfunctioncontrolsetilinstrumentedcodemap-method"></a><span data-ttu-id="8a1d2-102">Metodo ICorProfilerFunctionControl::SetILInstrumentedCodeMap</span><span class="sxs-lookup"><span data-stu-id="8a1d2-102">ICorProfilerFunctionControl::SetILInstrumentedCodeMap Method</span></span>
<span data-ttu-id="8a1d2-103">Imposta una mappa del codice per la funzione specificata usando le voci della mappa CIL (Common Intermediate Language) specificate.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-103">Sets a code map for the specified function by using the specified Common Intermediate Language (CIL) map entries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a1d2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8a1d2-104">Syntax</span></span>  
  
```  
HRESULT SetILInstrumentedCodeMap(  
    [in]   ULONG      cILMapEntries,  
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a1d2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8a1d2-105">Parameters</span></span>  
 `cILMapEntries`  
 <span data-ttu-id="8a1d2-106">[in] Numero di voci nella mappa.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-106">[in] The number of entries in the map.</span></span>  
  
 `rgILMapEntries`  
 <span data-ttu-id="8a1d2-107">[in] Matrice allocata dal chiamante di voci COR_IL_MAP.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-107">[in] The caller-allocated array of COR_IL_MAP  entries.</span></span> <span data-ttu-id="8a1d2-108">L'interpretazione di queste voci è uguali a quelle per il [ICorProfilerInfo:: SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="8a1d2-108">The interpretation of these entries is the same as for the [ICorProfilerInfo::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a1d2-109">Note</span><span class="sxs-lookup"><span data-stu-id="8a1d2-109">Remarks</span></span>  
 <span data-ttu-id="8a1d2-110">Imposta il mapping chiamando questo metodo consente al debugger di recuperare il mapping chiamando [ICorDebugILCode2::GetInstrumentedILMap](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md).</span><span class="sxs-lookup"><span data-stu-id="8a1d2-110">Setting the mapping by calling this method allows the debugger to retrieve the mapping by calling [ICorDebugILCode2::GetInstrumentedILMap](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md).</span></span> <span data-ttu-id="8a1d2-111">Il debugger potrà anche usare il mapping internamente durante il calcolo degli offset IL per le analisi dello stack e la durata delle variabili.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-111">It also allows the debugger to use the mapping internally when calculating IL offsets for stack traces and variable lifetimes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a1d2-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8a1d2-112">Requirements</span></span>  
 <span data-ttu-id="8a1d2-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a1d2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a1d2-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8a1d2-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8a1d2-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a1d2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a1d2-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a1d2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a1d2-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a1d2-117">See also</span></span>

- [<span data-ttu-id="8a1d2-118">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="8a1d2-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)

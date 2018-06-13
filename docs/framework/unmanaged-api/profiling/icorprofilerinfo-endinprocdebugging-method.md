---
title: Metodo ICorProfilerInfo::EndInprocDebugging
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.EndInprocDebugging
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::EndInprocDebugging
helpviewer_keywords:
- ICorProfilerInfo::EndInprocDebugging method [.NET Framework profiling]
- EndInprocDebugging method [.NET Framework profiling]
ms.assetid: 35bc1188-9767-4141-8038-60ea015b99ac
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cbf7e2e7de54b065f25f3a1873d760ab5051cc91
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452611"
---
# <a name="icorprofilerinfoendinprocdebugging-method"></a><span data-ttu-id="4825c-102">Metodo ICorProfilerInfo::EndInprocDebugging</span><span class="sxs-lookup"><span data-stu-id="4825c-102">ICorProfilerInfo::EndInprocDebugging Method</span></span>
<span data-ttu-id="4825c-103">Arresta una sessione di debug in-process.</span><span class="sxs-lookup"><span data-stu-id="4825c-103">Shuts down an in-process debugging session.</span></span> <span data-ttu-id="4825c-104">Questo metodo è obsoleto in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="4825c-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4825c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4825c-105">Syntax</span></span>  
  
```  
HRESULT EndInprocDebugging(  
    [in]  DWORD dwProfilerContext);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4825c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="4825c-106">Parameters</span></span>  
 `dwProfilerContext`  
 <span data-ttu-id="4825c-107">[in] Un valore che identifica la sessione di debug.</span><span class="sxs-lookup"><span data-stu-id="4825c-107">[in] A value that identifies the debugging session.</span></span> <span data-ttu-id="4825c-108">Questo valore deve essere uguale a quello ricevuto il [ICorProfilerInfo:: BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="4825c-108">This value must be the same as that received in the [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4825c-109">Note</span><span class="sxs-lookup"><span data-stu-id="4825c-109">Remarks</span></span>  
 <span data-ttu-id="4825c-110">È necessario chiamare [ICorProfilerInfo:: BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) e `EndInprocDebugging` entro lo stesso metodo di callback.</span><span class="sxs-lookup"><span data-stu-id="4825c-110">You must call [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) and `EndInprocDebugging` within the same callback method.</span></span>  
  
 <span data-ttu-id="4825c-111">I servizi di debug di Common Language Runtime è supportato il debug in-process limitato in .NET Framework versioni 1.0 e 1.1.</span><span class="sxs-lookup"><span data-stu-id="4825c-111">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="4825c-112">Debug in-process è abilitato un profiler di usare le parti di verifica dell'API di debug.</span><span class="sxs-lookup"><span data-stu-id="4825c-112">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="4825c-113">Tuttavia, a causa di feedback dei clienti, debug in-process è stato rimosso da .NET Framework versione 2.0 e sostituito con un set di funzionalità più in linea con l'API di profilatura.</span><span class="sxs-lookup"><span data-stu-id="4825c-113">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4825c-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4825c-114">Requirements</span></span>  
 <span data-ttu-id="4825c-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4825c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4825c-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4825c-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4825c-117">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="4825c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4825c-118">**Versione di .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="4825c-118">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4825c-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4825c-119">See Also</span></span>  
 [<span data-ttu-id="4825c-120">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="4825c-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)

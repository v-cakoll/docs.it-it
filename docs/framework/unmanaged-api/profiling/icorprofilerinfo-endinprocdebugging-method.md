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
ms.openlocfilehash: 09b1b81bde486db67acede99e0d67ff85cb01bae
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447760"
---
# <a name="icorprofilerinfoendinprocdebugging-method"></a><span data-ttu-id="45d65-102">Metodo ICorProfilerInfo::EndInprocDebugging</span><span class="sxs-lookup"><span data-stu-id="45d65-102">ICorProfilerInfo::EndInprocDebugging Method</span></span>
<span data-ttu-id="45d65-103">Arresta una sessione di debug in-process.</span><span class="sxs-lookup"><span data-stu-id="45d65-103">Shuts down an in-process debugging session.</span></span> <span data-ttu-id="45d65-104">Questo metodo è obsoleto nella versione .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="45d65-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45d65-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="45d65-105">Syntax</span></span>  
  
```cpp  
HRESULT EndInprocDebugging(  
    [in]  DWORD dwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45d65-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="45d65-106">Parameters</span></span>  
 `dwProfilerContext`  
 <span data-ttu-id="45d65-107">in Valore che identifica la sessione di debug.</span><span class="sxs-lookup"><span data-stu-id="45d65-107">[in] A value that identifies the debugging session.</span></span> <span data-ttu-id="45d65-108">Questo valore deve corrispondere a quello ricevuto nel metodo [ICorProfilerInfo:: BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) .</span><span class="sxs-lookup"><span data-stu-id="45d65-108">This value must be the same as that received in the [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="45d65-109">Note</span><span class="sxs-lookup"><span data-stu-id="45d65-109">Remarks</span></span>  
 <span data-ttu-id="45d65-110">È necessario chiamare [ICorProfilerInfo:: BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) e `EndInprocDebugging` nello stesso metodo di callback.</span><span class="sxs-lookup"><span data-stu-id="45d65-110">You must call [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) and `EndInprocDebugging` within the same callback method.</span></span>  
  
 <span data-ttu-id="45d65-111">I servizi di debug CLR supportano il debug in-process limitato nelle versioni .NET Framework 1,0 e 1,1.</span><span class="sxs-lookup"><span data-stu-id="45d65-111">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="45d65-112">Il debug in-process ha consentito a un profiler di usare le parti di ispezione dell'API di debug.</span><span class="sxs-lookup"><span data-stu-id="45d65-112">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="45d65-113">Tuttavia, a causa dei suggerimenti dei clienti, il debug in-process è stato rimosso dalla .NET Framework nella versione 2,0 e sostituito con un set di funzionalità più in linea con l'API di profilatura.</span><span class="sxs-lookup"><span data-stu-id="45d65-113">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45d65-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="45d65-114">Requirements</span></span>  
 <span data-ttu-id="45d65-115">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45d65-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45d65-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="45d65-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="45d65-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45d65-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45d65-118">**Versione .NET Framework:** 1,0</span><span class="sxs-lookup"><span data-stu-id="45d65-118">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45d65-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45d65-119">See also</span></span>

- [<span data-ttu-id="45d65-120">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="45d65-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)

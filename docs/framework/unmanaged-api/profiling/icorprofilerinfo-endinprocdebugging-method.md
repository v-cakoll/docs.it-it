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
ms.openlocfilehash: 8a15843e9169442d89996375ee85f62b38f92e30
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864258"
---
# <a name="icorprofilerinfoendinprocdebugging-method"></a><span data-ttu-id="9f5d1-102">Metodo ICorProfilerInfo::EndInprocDebugging</span><span class="sxs-lookup"><span data-stu-id="9f5d1-102">ICorProfilerInfo::EndInprocDebugging Method</span></span>
<span data-ttu-id="9f5d1-103">Arresta una sessione di debug in-process.</span><span class="sxs-lookup"><span data-stu-id="9f5d1-103">Shuts down an in-process debugging session.</span></span> <span data-ttu-id="9f5d1-104">Questo metodo è obsoleto nella versione .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="9f5d1-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f5d1-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9f5d1-105">Syntax</span></span>  
  
```cpp  
HRESULT EndInprocDebugging(  
    [in]  DWORD dwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f5d1-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="9f5d1-106">Parameters</span></span>  
 `dwProfilerContext`  
 <span data-ttu-id="9f5d1-107">in Valore che identifica la sessione di debug.</span><span class="sxs-lookup"><span data-stu-id="9f5d1-107">[in] A value that identifies the debugging session.</span></span> <span data-ttu-id="9f5d1-108">Questo valore deve corrispondere a quello ricevuto nel metodo [ICorProfilerInfo:: BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9f5d1-108">This value must be the same as that received in the [ICorProfilerInfo::BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f5d1-109">Note</span><span class="sxs-lookup"><span data-stu-id="9f5d1-109">Remarks</span></span>  
 <span data-ttu-id="9f5d1-110">È necessario chiamare [ICorProfilerInfo:: BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md) e `EndInprocDebugging` nello stesso metodo di callback.</span><span class="sxs-lookup"><span data-stu-id="9f5d1-110">You must call [ICorProfilerInfo::BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md) and `EndInprocDebugging` within the same callback method.</span></span>  
  
 <span data-ttu-id="9f5d1-111">I servizi di debug CLR supportano il debug in-process limitato nelle versioni .NET Framework 1,0 e 1,1.</span><span class="sxs-lookup"><span data-stu-id="9f5d1-111">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="9f5d1-112">Il debug in-process ha consentito a un profiler di usare le parti di ispezione dell'API di debug.</span><span class="sxs-lookup"><span data-stu-id="9f5d1-112">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="9f5d1-113">Tuttavia, a causa dei suggerimenti dei clienti, il debug in-process è stato rimosso dalla .NET Framework nella versione 2,0 e sostituito con un set di funzionalità più in linea con l'API di profilatura.</span><span class="sxs-lookup"><span data-stu-id="9f5d1-113">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f5d1-114">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="9f5d1-114">Requirements</span></span>  
 <span data-ttu-id="9f5d1-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f5d1-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f5d1-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9f5d1-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9f5d1-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f5d1-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f5d1-118">**Versione .NET Framework:** 1,0</span><span class="sxs-lookup"><span data-stu-id="9f5d1-118">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f5d1-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f5d1-119">See also</span></span>

- [<span data-ttu-id="9f5d1-120">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="9f5d1-120">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)

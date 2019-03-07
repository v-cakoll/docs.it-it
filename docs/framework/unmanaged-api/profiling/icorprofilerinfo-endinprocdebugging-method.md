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
ms.openlocfilehash: f86c680a10a3dcb1009b4f0cedd777ab9da5ac1f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501747"
---
# <a name="icorprofilerinfoendinprocdebugging-method"></a><span data-ttu-id="391d0-102">Metodo ICorProfilerInfo::EndInprocDebugging</span><span class="sxs-lookup"><span data-stu-id="391d0-102">ICorProfilerInfo::EndInprocDebugging Method</span></span>
<span data-ttu-id="391d0-103">Arresta una sessione di debug in-process.</span><span class="sxs-lookup"><span data-stu-id="391d0-103">Shuts down an in-process debugging session.</span></span> <span data-ttu-id="391d0-104">Questo metodo è obsoleto in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="391d0-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="391d0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="391d0-105">Syntax</span></span>  
  
```  
HRESULT EndInprocDebugging(  
    [in]  DWORD dwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="391d0-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="391d0-106">Parameters</span></span>  
 `dwProfilerContext`  
 <span data-ttu-id="391d0-107">[in] Un valore che identifica la sessione di debug.</span><span class="sxs-lookup"><span data-stu-id="391d0-107">[in] A value that identifies the debugging session.</span></span> <span data-ttu-id="391d0-108">Questo valore deve essere uguale a quello ricevuto nel [BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="391d0-108">This value must be the same as that received in the [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="391d0-109">Note</span><span class="sxs-lookup"><span data-stu-id="391d0-109">Remarks</span></span>  
 <span data-ttu-id="391d0-110">È necessario chiamare [BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) e `EndInprocDebugging` entro lo stesso metodo di callback.</span><span class="sxs-lookup"><span data-stu-id="391d0-110">You must call [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) and `EndInprocDebugging` within the same callback method.</span></span>  
  
 <span data-ttu-id="391d0-111">I servizi di debug CLR supportavano il debug in-process limitata nelle versioni 1.0 e 1.1 di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="391d0-111">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="391d0-112">Per attivare un profiler di usare le parti di verifica dell'API di debug, il debug in-process.</span><span class="sxs-lookup"><span data-stu-id="391d0-112">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="391d0-113">Tuttavia, a causa di commenti e suggerimenti dei clienti, debug in-process è stati rimossi da .NET Framework versione 2.0 e sostituito con un set di funzionalità che è più in linea con l'API di profilatura.</span><span class="sxs-lookup"><span data-stu-id="391d0-113">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="391d0-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="391d0-114">Requirements</span></span>  
 <span data-ttu-id="391d0-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="391d0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="391d0-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="391d0-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="391d0-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="391d0-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="391d0-118">**Versione di .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="391d0-118">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="391d0-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="391d0-119">See also</span></span>
- [<span data-ttu-id="391d0-120">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="391d0-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)

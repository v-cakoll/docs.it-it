---
title: Metodo ICorProfilerInfo::BeginInprocDebugging
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.BeginInprocDebugging
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::BeginInprocDebugging
helpviewer_keywords:
- BeginInprocDebugging method [.NET Framework profiling]
- ICorProfilerInfo::BeginInprocDebugging method [.NET Framework profiling]
ms.assetid: c5c82c69-99f8-4447-aee0-42cca0a5eb5c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f12442eb5596ff3dca49cf24e27040f3e92d3a7c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991926"
---
# <a name="icorprofilerinfobegininprocdebugging-method"></a><span data-ttu-id="c376f-102">Metodo ICorProfilerInfo::BeginInprocDebugging</span><span class="sxs-lookup"><span data-stu-id="c376f-102">ICorProfilerInfo::BeginInprocDebugging Method</span></span>
<span data-ttu-id="c376f-103">Consente di inizializzare il supporto del debug in-process.</span><span class="sxs-lookup"><span data-stu-id="c376f-103">Initializes in-process debugging support.</span></span> <span data-ttu-id="c376f-104">Questo metodo è obsoleto in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="c376f-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c376f-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c376f-105">Syntax</span></span>  
  
```  
HRESULT BeginInprocDebugging(  
    [in]  BOOL   fThisThreadOnly,  
    [out] DWORD *pdwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c376f-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="c376f-106">Parameters</span></span>  
 `fThisThreadOnly`  
 <span data-ttu-id="c376f-107">[in] Impostare questo valore su `true` per inizializzare il supporto del debug solo il thread corrente; impostato su `false` per inizializzare il supporto del debug per tutti i thread.</span><span class="sxs-lookup"><span data-stu-id="c376f-107">[in] Set this value to `true` to initialize debugging support for only the current thread; set it to `false` to initialize debugging support for all threads.</span></span>  
  
 `pdwProfilerContext`  
 <span data-ttu-id="c376f-108">[out] Il puntatore su un valore restituito che identifica la sessione di debug.</span><span class="sxs-lookup"><span data-stu-id="c376f-108">[out] The pointer to a returned value that identifies the debugging session.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c376f-109">Note</span><span class="sxs-lookup"><span data-stu-id="c376f-109">Remarks</span></span>  
 <span data-ttu-id="c376f-110">I servizi di debug CLR supportavano il debug in-process limitata nelle versioni 1.0 e 1.1 di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c376f-110">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="c376f-111">Per attivare un profiler di usare le parti di verifica dell'API di debug, il debug in-process.</span><span class="sxs-lookup"><span data-stu-id="c376f-111">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="c376f-112">Tuttavia, a causa di commenti e suggerimenti dei clienti, debug in-process è stati rimossi da .NET Framework versione 2.0 e sostituito con un set di funzionalità che è più in linea con l'API di profilatura.</span><span class="sxs-lookup"><span data-stu-id="c376f-112">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c376f-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c376f-113">Requirements</span></span>  
 <span data-ttu-id="c376f-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c376f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c376f-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c376f-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c376f-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c376f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c376f-117">**Versione di .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="c376f-117">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c376f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c376f-118">See also</span></span>

- [<span data-ttu-id="c376f-119">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="c376f-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)

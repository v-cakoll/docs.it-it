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
ms.openlocfilehash: c14979fa711145b9f1a134f90d7450b24e6d8a15
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864297"
---
# <a name="icorprofilerinfobegininprocdebugging-method"></a><span data-ttu-id="3f6c5-102">Metodo ICorProfilerInfo::BeginInprocDebugging</span><span class="sxs-lookup"><span data-stu-id="3f6c5-102">ICorProfilerInfo::BeginInprocDebugging Method</span></span>
<span data-ttu-id="3f6c5-103">Inizializza il supporto per il debug in-process.</span><span class="sxs-lookup"><span data-stu-id="3f6c5-103">Initializes in-process debugging support.</span></span> <span data-ttu-id="3f6c5-104">Questo metodo è obsoleto nella versione .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="3f6c5-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f6c5-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3f6c5-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginInprocDebugging(  
    [in]  BOOL   fThisThreadOnly,  
    [out] DWORD *pdwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f6c5-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="3f6c5-106">Parameters</span></span>  
 `fThisThreadOnly`  
 <span data-ttu-id="3f6c5-107">in Impostare questo valore su `true` per inizializzare il supporto del debug solo per il thread corrente. impostarlo su `false` per inizializzare il supporto del debug per tutti i thread.</span><span class="sxs-lookup"><span data-stu-id="3f6c5-107">[in] Set this value to `true` to initialize debugging support for only the current thread; set it to `false` to initialize debugging support for all threads.</span></span>  
  
 `pdwProfilerContext`  
 <span data-ttu-id="3f6c5-108">out Puntatore a un valore restituito che identifica la sessione di debug.</span><span class="sxs-lookup"><span data-stu-id="3f6c5-108">[out] The pointer to a returned value that identifies the debugging session.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f6c5-109">Note</span><span class="sxs-lookup"><span data-stu-id="3f6c5-109">Remarks</span></span>  
 <span data-ttu-id="3f6c5-110">I servizi di debug CLR supportano il debug in-process limitato nelle versioni .NET Framework 1,0 e 1,1.</span><span class="sxs-lookup"><span data-stu-id="3f6c5-110">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="3f6c5-111">Il debug in-process ha consentito a un profiler di usare le parti di ispezione dell'API di debug.</span><span class="sxs-lookup"><span data-stu-id="3f6c5-111">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="3f6c5-112">Tuttavia, a causa dei suggerimenti dei clienti, il debug in-process è stato rimosso dalla .NET Framework nella versione 2,0 e sostituito con un set di funzionalità più in linea con l'API di profilatura.</span><span class="sxs-lookup"><span data-stu-id="3f6c5-112">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f6c5-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="3f6c5-113">Requirements</span></span>  
 <span data-ttu-id="3f6c5-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f6c5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f6c5-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3f6c5-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3f6c5-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f6c5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f6c5-117">**Versione .NET Framework:** 1,0</span><span class="sxs-lookup"><span data-stu-id="3f6c5-117">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f6c5-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f6c5-118">See also</span></span>

- [<span data-ttu-id="3f6c5-119">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="3f6c5-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)

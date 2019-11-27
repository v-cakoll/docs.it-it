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
ms.openlocfilehash: fffc028c7706c86e8384483cc92ebad90b292861
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447745"
---
# <a name="icorprofilerinfobegininprocdebugging-method"></a><span data-ttu-id="95e43-102">Metodo ICorProfilerInfo::BeginInprocDebugging</span><span class="sxs-lookup"><span data-stu-id="95e43-102">ICorProfilerInfo::BeginInprocDebugging Method</span></span>
<span data-ttu-id="95e43-103">Inizializza il supporto per il debug in-process.</span><span class="sxs-lookup"><span data-stu-id="95e43-103">Initializes in-process debugging support.</span></span> <span data-ttu-id="95e43-104">Questo metodo è obsoleto nella versione .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="95e43-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95e43-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="95e43-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginInprocDebugging(  
    [in]  BOOL   fThisThreadOnly,  
    [out] DWORD *pdwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95e43-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="95e43-106">Parameters</span></span>  
 `fThisThreadOnly`  
 <span data-ttu-id="95e43-107">in Impostare questo valore su `true` per inizializzare il supporto del debug solo per il thread corrente. impostarlo su `false` per inizializzare il supporto del debug per tutti i thread.</span><span class="sxs-lookup"><span data-stu-id="95e43-107">[in] Set this value to `true` to initialize debugging support for only the current thread; set it to `false` to initialize debugging support for all threads.</span></span>  
  
 `pdwProfilerContext`  
 <span data-ttu-id="95e43-108">out Puntatore a un valore restituito che identifica la sessione di debug.</span><span class="sxs-lookup"><span data-stu-id="95e43-108">[out] The pointer to a returned value that identifies the debugging session.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95e43-109">Note</span><span class="sxs-lookup"><span data-stu-id="95e43-109">Remarks</span></span>  
 <span data-ttu-id="95e43-110">I servizi di debug CLR supportano il debug in-process limitato nelle versioni .NET Framework 1,0 e 1,1.</span><span class="sxs-lookup"><span data-stu-id="95e43-110">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="95e43-111">Il debug in-process ha consentito a un profiler di usare le parti di ispezione dell'API di debug.</span><span class="sxs-lookup"><span data-stu-id="95e43-111">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="95e43-112">Tuttavia, a causa dei suggerimenti dei clienti, il debug in-process è stato rimosso dalla .NET Framework nella versione 2,0 e sostituito con un set di funzionalità più in linea con l'API di profilatura.</span><span class="sxs-lookup"><span data-stu-id="95e43-112">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95e43-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="95e43-113">Requirements</span></span>  
 <span data-ttu-id="95e43-114">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95e43-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95e43-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="95e43-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="95e43-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95e43-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95e43-117">**Versione .NET Framework:** 1,0</span><span class="sxs-lookup"><span data-stu-id="95e43-117">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95e43-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95e43-118">See also</span></span>

- [<span data-ttu-id="95e43-119">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="95e43-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)

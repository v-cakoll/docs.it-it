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
ms.openlocfilehash: 82e798e1a31f771c63e71f2a85f8cbb684b237bd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33462390"
---
# <a name="icorprofilerinfobegininprocdebugging-method"></a><span data-ttu-id="02373-102">Metodo ICorProfilerInfo::BeginInprocDebugging</span><span class="sxs-lookup"><span data-stu-id="02373-102">ICorProfilerInfo::BeginInprocDebugging Method</span></span>
<span data-ttu-id="02373-103">Inizializza il supporto del debug in-process.</span><span class="sxs-lookup"><span data-stu-id="02373-103">Initializes in-process debugging support.</span></span> <span data-ttu-id="02373-104">Questo metodo è obsoleto in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="02373-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02373-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="02373-105">Syntax</span></span>  
  
```  
HRESULT BeginInprocDebugging(  
    [in]  BOOL   fThisThreadOnly,  
    [out] DWORD *pdwProfilerContext);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="02373-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="02373-106">Parameters</span></span>  
 `fThisThreadOnly`  
 <span data-ttu-id="02373-107">[in] Impostare questo valore su `true` per inizializzare il supporto del debug solo per il thread corrente; impostarlo su `false` per inizializzare il supporto del debug per tutti i thread.</span><span class="sxs-lookup"><span data-stu-id="02373-107">[in] Set this value to `true` to initialize debugging support for only the current thread; set it to `false` to initialize debugging support for all threads.</span></span>  
  
 `pdwProfilerContext`  
 <span data-ttu-id="02373-108">[out] Puntatore a un valore restituito che identifica la sessione di debug.</span><span class="sxs-lookup"><span data-stu-id="02373-108">[out] The pointer to a returned value that identifies the debugging session.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02373-109">Note</span><span class="sxs-lookup"><span data-stu-id="02373-109">Remarks</span></span>  
 <span data-ttu-id="02373-110">I servizi di debug di Common Language Runtime è supportato il debug in-process limitato in .NET Framework versioni 1.0 e 1.1.</span><span class="sxs-lookup"><span data-stu-id="02373-110">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="02373-111">Debug in-process è abilitato un profiler di usare le parti di verifica dell'API di debug.</span><span class="sxs-lookup"><span data-stu-id="02373-111">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="02373-112">Tuttavia, a causa di feedback dei clienti, debug in-process è stato rimosso da .NET Framework versione 2.0 e sostituito con un set di funzionalità più in linea con l'API di profilatura.</span><span class="sxs-lookup"><span data-stu-id="02373-112">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02373-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="02373-113">Requirements</span></span>  
 <span data-ttu-id="02373-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02373-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02373-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="02373-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="02373-116">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="02373-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02373-117">**Versione di .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="02373-117">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02373-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02373-118">See Also</span></span>  
 [<span data-ttu-id="02373-119">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="02373-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)

---
title: Metodo ICorProfilerInfo::ForceGC
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.ForceGC
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::ForceGC
helpviewer_keywords:
- ICorProfilerInfo::ForceGC method [.NET Framework profiling]
- ForceGC method [.NET Framework profiling]
ms.assetid: 0da1ef80-d242-4636-87d0-43e0470b342a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5672d1b89b4260d1ebfbf444deb2702f215a0e95
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59078083"
---
# <a name="icorprofilerinfoforcegc-method"></a><span data-ttu-id="cf404-102">Metodo ICorProfilerInfo::ForceGC</span><span class="sxs-lookup"><span data-stu-id="cf404-102">ICorProfilerInfo::ForceGC Method</span></span>
<span data-ttu-id="cf404-103">Forza il garbage collection a cui si verificano all'interno di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="cf404-103">Forces garbage collection to occur within the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf404-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cf404-104">Syntax</span></span>  
  
```  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a><span data-ttu-id="cf404-105">Note</span><span class="sxs-lookup"><span data-stu-id="cf404-105">Remarks</span></span>  
 <span data-ttu-id="cf404-106">Il `ForceGC` metodo deve essere chiamato solo da un thread che non ha mai eseguito il codice gestito e non dispone di qualsiasi callback del profiler per il relativo stack.</span><span class="sxs-lookup"><span data-stu-id="cf404-106">The `ForceGC` method must be called only from a thread that has never run managed code and does not have any profiler callbacks on its stack.</span></span> <span data-ttu-id="cf404-107">L'implementazione più semplice consiste nel creare un thread separato all'interno del profiler che chiama `ForceGC` quando riceve un segnale.</span><span class="sxs-lookup"><span data-stu-id="cf404-107">The most convenient implementation is to create a separate thread within the profiler that calls `ForceGC` when signaled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf404-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cf404-108">Requirements</span></span>  
 <span data-ttu-id="cf404-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf404-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf404-110">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cf404-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cf404-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf404-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf404-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf404-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf404-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf404-113">See also</span></span>

- [<span data-ttu-id="cf404-114">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="cf404-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)

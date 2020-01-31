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
ms.openlocfilehash: e1fe38419cda328c919f0840d51cf6336919aa60
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864195"
---
# <a name="icorprofilerinfoforcegc-method"></a><span data-ttu-id="eedeb-102">Metodo ICorProfilerInfo::ForceGC</span><span class="sxs-lookup"><span data-stu-id="eedeb-102">ICorProfilerInfo::ForceGC Method</span></span>
<span data-ttu-id="eedeb-103">Impone la Garbage Collection all'interno del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="eedeb-103">Forces garbage collection to occur within the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eedeb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eedeb-104">Syntax</span></span>  
  
```cpp  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a><span data-ttu-id="eedeb-105">Note</span><span class="sxs-lookup"><span data-stu-id="eedeb-105">Remarks</span></span>  
 <span data-ttu-id="eedeb-106">Il metodo di `ForceGC` deve essere chiamato solo da un thread che non esegue mai codice gestito e che non dispone di callback del profiler nello stack.</span><span class="sxs-lookup"><span data-stu-id="eedeb-106">The `ForceGC` method must be called only from a thread that has never run managed code and does not have any profiler callbacks on its stack.</span></span> <span data-ttu-id="eedeb-107">L'implementazione più semplice consiste nel creare un thread separato nel profiler che chiama `ForceGC` quando viene segnalato.</span><span class="sxs-lookup"><span data-stu-id="eedeb-107">The most convenient implementation is to create a separate thread within the profiler that calls `ForceGC` when signaled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eedeb-108">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="eedeb-108">Requirements</span></span>  
 <span data-ttu-id="eedeb-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eedeb-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eedeb-110">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="eedeb-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="eedeb-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eedeb-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eedeb-112">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eedeb-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eedeb-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eedeb-113">See also</span></span>

- [<span data-ttu-id="eedeb-114">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="eedeb-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)

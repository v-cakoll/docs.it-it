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
ms.openlocfilehash: 9bc6619f3ef383c7bf60a310a87f056cfc43cddf
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498674"
---
# <a name="icorprofilerinfoforcegc-method"></a><span data-ttu-id="97246-102">Metodo ICorProfilerInfo::ForceGC</span><span class="sxs-lookup"><span data-stu-id="97246-102">ICorProfilerInfo::ForceGC Method</span></span>
<span data-ttu-id="97246-103">Impone la Garbage Collection all'interno del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="97246-103">Forces garbage collection to occur within the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97246-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="97246-104">Syntax</span></span>  
  
```cpp  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a><span data-ttu-id="97246-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="97246-105">Remarks</span></span>  
 <span data-ttu-id="97246-106">Il `ForceGC` metodo deve essere chiamato solo da un thread che non ha mai eseguito codice gestito e che non dispone di callback del profiler nello stack.</span><span class="sxs-lookup"><span data-stu-id="97246-106">The `ForceGC` method must be called only from a thread that has never run managed code and does not have any profiler callbacks on its stack.</span></span> <span data-ttu-id="97246-107">L'implementazione più semplice consiste nel creare un thread separato all'interno del profiler che chiama `ForceGC` quando segnalato.</span><span class="sxs-lookup"><span data-stu-id="97246-107">The most convenient implementation is to create a separate thread within the profiler that calls `ForceGC` when signaled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97246-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="97246-108">Requirements</span></span>  
 <span data-ttu-id="97246-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97246-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97246-110">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="97246-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="97246-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97246-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97246-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97246-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97246-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97246-113">See also</span></span>

- [<span data-ttu-id="97246-114">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="97246-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)

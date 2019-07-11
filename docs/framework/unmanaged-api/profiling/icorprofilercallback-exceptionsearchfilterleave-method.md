---
title: Metodo ICorProfilerCallback::ExceptionSearchFilterLeave
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFilterLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFilterLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionSearchFilterLeave method [.NET Framework profiling]
- ExceptionSearchFilterLeave method [.NET Framework profiling]
ms.assetid: c28a2a82-dd11-4385-843f-b509fb61753b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c71eb61dba5b62fcfed21d3500df70c1a699d42c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756090"
---
# <a name="icorprofilercallbackexceptionsearchfilterleave-method"></a><span data-ttu-id="d55fd-102">Metodo ICorProfilerCallback::ExceptionSearchFilterLeave</span><span class="sxs-lookup"><span data-stu-id="d55fd-102">ICorProfilerCallback::ExceptionSearchFilterLeave Method</span></span>
<span data-ttu-id="d55fd-103">Notifica al profiler che un filtro utente appena terminata l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d55fd-103">Notifies the profiler that a user filter has just finished executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d55fd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d55fd-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFilterLeave();  
```  
  
## <a name="requirements"></a><span data-ttu-id="d55fd-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d55fd-105">Requirements</span></span>  
 <span data-ttu-id="d55fd-106">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d55fd-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d55fd-107">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d55fd-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d55fd-108">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d55fd-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d55fd-109">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d55fd-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d55fd-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d55fd-110">See also</span></span>

- [<span data-ttu-id="d55fd-111">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="d55fd-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="d55fd-112">Metodo ExceptionSearchFilterEnter</span><span class="sxs-lookup"><span data-stu-id="d55fd-112">ExceptionSearchFilterEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)

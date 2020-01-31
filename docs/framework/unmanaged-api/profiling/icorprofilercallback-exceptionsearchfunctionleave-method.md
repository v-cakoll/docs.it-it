---
title: Metodo ICorProfilerCallback::ExceptionSearchFunctionLeave
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFunctionLeave
helpviewer_keywords:
- ExceptionSearchFunctionLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFunctionLeave method [.NET Framework profiling]
ms.assetid: 01de7ac6-0aad-42ef-bf93-50737667b0a4
topic_type:
- apiref
ms.openlocfilehash: bbd4c9e40f257cc66b638ba01ef8e51205922ece
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866390"
---
# <a name="icorprofilercallbackexceptionsearchfunctionleave-method"></a><span data-ttu-id="2d523-102">Metodo ICorProfilerCallback::ExceptionSearchFunctionLeave</span><span class="sxs-lookup"><span data-stu-id="2d523-102">ICorProfilerCallback::ExceptionSearchFunctionLeave Method</span></span>
<span data-ttu-id="2d523-103">Notifica al profiler che la fase di ricerca della gestione delle eccezioni ha terminato la ricerca di una funzione.</span><span class="sxs-lookup"><span data-stu-id="2d523-103">Notifies the profiler that the search phase of exception handling has finished searching a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d523-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2d523-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFunctionLeave();  
```  
  
## <a name="requirements"></a><span data-ttu-id="2d523-105">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="2d523-105">Requirements</span></span>  
 <span data-ttu-id="2d523-106">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d523-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d523-107">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2d523-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2d523-108">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d523-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d523-109">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d523-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d523-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d523-110">See also</span></span>

- [<span data-ttu-id="2d523-111">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="2d523-111">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="2d523-112">Metodo ExceptionSearchFunctionEnter</span><span class="sxs-lookup"><span data-stu-id="2d523-112">ExceptionSearchFunctionEnter Method</span></span>](icorprofilercallback-exceptionsearchfunctionenter-method.md)

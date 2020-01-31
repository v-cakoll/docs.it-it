---
title: Metodo ICorProfilerCallback::ExceptionCLRCatcherExecute
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCLRCatcherExecute
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherExecute
helpviewer_keywords:
- ExceptionCLRCatcherExecute method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionCLRCatcherExecute method [.NET Framework profiling]
ms.assetid: aaac8f98-5cf4-42c7-b04b-556cce367e36
topic_type:
- apiref
ms.openlocfilehash: f14dff33217656c35379a214f007ccb3642ef4b1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866455"
---
# <a name="icorprofilercallbackexceptionclrcatcherexecute-method"></a><span data-ttu-id="4929f-102">Metodo ICorProfilerCallback::ExceptionCLRCatcherExecute</span><span class="sxs-lookup"><span data-stu-id="4929f-102">ICorProfilerCallback::ExceptionCLRCatcherExecute Method</span></span>
<span data-ttu-id="4929f-103">Chiamato quando un blocco `catch` per un'eccezione viene eseguito all'interno della Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="4929f-103">Called when a `catch` block for an exception is executed inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="4929f-104">Questo metodo è obsoleto nella versione .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="4929f-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4929f-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4929f-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherExecute();  
```  
  
## <a name="requirements"></a><span data-ttu-id="4929f-106">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="4929f-106">Requirements</span></span>  
 <span data-ttu-id="4929f-107">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4929f-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4929f-108">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4929f-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4929f-109">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4929f-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4929f-110">**Versioni .NET Framework:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="4929f-110">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4929f-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4929f-111">See also</span></span>

- [<span data-ttu-id="4929f-112">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="4929f-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="4929f-113">Metodo ExceptionCLRCatcherFound</span><span class="sxs-lookup"><span data-stu-id="4929f-113">ExceptionCLRCatcherFound Method</span></span>](icorprofilercallback-exceptionclrcatcherfound-method.md)

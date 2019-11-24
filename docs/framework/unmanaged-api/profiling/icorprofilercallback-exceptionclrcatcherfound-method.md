---
title: Metodo ICorProfilerCallback::ExceptionCLRCatcherFound
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCLRCatcherFound
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherFound
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherFound method [.NET Framework profiling]
- ExceptionCLRCatcherFound method [.NET Framework profiling]
ms.assetid: 73fe8b4b-8f9a-4ba5-a10c-b26521396a66
topic_type:
- apiref
ms.openlocfilehash: ef5122d49c428af4faa27f3827a5c60721ef0f74
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435833"
---
# <a name="icorprofilercallbackexceptionclrcatcherfound-method"></a><span data-ttu-id="31057-102">Metodo ICorProfilerCallback::ExceptionCLRCatcherFound</span><span class="sxs-lookup"><span data-stu-id="31057-102">ICorProfilerCallback::ExceptionCLRCatcherFound Method</span></span>
<span data-ttu-id="31057-103">Called when a `catch` block for an exception is found inside the common language runtime (CLR) itself.</span><span class="sxs-lookup"><span data-stu-id="31057-103">Called when a `catch` block for an exception is found inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="31057-104">This method is obsolete in the .NET Framework version 2.0.</span><span class="sxs-lookup"><span data-stu-id="31057-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31057-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="31057-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherFound();  
```  
  
## <a name="requirements"></a><span data-ttu-id="31057-106">Requisiti</span><span class="sxs-lookup"><span data-stu-id="31057-106">Requirements</span></span>  
 <span data-ttu-id="31057-107">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31057-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31057-108">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="31057-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="31057-109">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31057-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31057-110">**.NET Framework Version:** 1.0</span><span class="sxs-lookup"><span data-stu-id="31057-110">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31057-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31057-111">See also</span></span>

- [<span data-ttu-id="31057-112">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="31057-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="31057-113">Metodo ExceptionCLRCatcherExecute</span><span class="sxs-lookup"><span data-stu-id="31057-113">ExceptionCLRCatcherExecute Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherexecute-method.md)

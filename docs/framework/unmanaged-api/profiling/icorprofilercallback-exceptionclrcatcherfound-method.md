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
ms.openlocfilehash: 4f4d53b086453adce38902518f2de3dde1f2812f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500247"
---
# <a name="icorprofilercallbackexceptionclrcatcherfound-method"></a><span data-ttu-id="530a1-102">Metodo ICorProfilerCallback::ExceptionCLRCatcherFound</span><span class="sxs-lookup"><span data-stu-id="530a1-102">ICorProfilerCallback::ExceptionCLRCatcherFound Method</span></span>
<span data-ttu-id="530a1-103">Chiamato quando `catch` viene trovato un blocco per un'eccezione all'interno del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="530a1-103">Called when a `catch` block for an exception is found inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="530a1-104">Questo metodo è obsoleto nella versione .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="530a1-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="530a1-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="530a1-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherFound();  
```  
  
## <a name="requirements"></a><span data-ttu-id="530a1-106">Requisiti</span><span class="sxs-lookup"><span data-stu-id="530a1-106">Requirements</span></span>  
 <span data-ttu-id="530a1-107">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="530a1-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="530a1-108">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="530a1-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="530a1-109">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="530a1-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="530a1-110">**Versione .NET Framework:** 1,0</span><span class="sxs-lookup"><span data-stu-id="530a1-110">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="530a1-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="530a1-111">See also</span></span>

- [<span data-ttu-id="530a1-112">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="530a1-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="530a1-113">Metodo ExceptionCLRCatcherExecute</span><span class="sxs-lookup"><span data-stu-id="530a1-113">ExceptionCLRCatcherExecute Method</span></span>](icorprofilercallback-exceptionclrcatcherexecute-method.md)

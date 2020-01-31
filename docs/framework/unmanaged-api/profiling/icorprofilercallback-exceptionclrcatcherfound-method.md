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
ms.openlocfilehash: a543e5119a3ad5580fb67c31dc0e59ab62eab571
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866492"
---
# <a name="icorprofilercallbackexceptionclrcatcherfound-method"></a><span data-ttu-id="5ee18-102">Metodo ICorProfilerCallback::ExceptionCLRCatcherFound</span><span class="sxs-lookup"><span data-stu-id="5ee18-102">ICorProfilerCallback::ExceptionCLRCatcherFound Method</span></span>
<span data-ttu-id="5ee18-103">Chiamato quando un blocco di `catch` per un'eccezione viene trovato all'interno della Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="5ee18-103">Called when a `catch` block for an exception is found inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="5ee18-104">Questo metodo è obsoleto nella versione .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="5ee18-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ee18-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5ee18-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherFound();  
```  
  
## <a name="requirements"></a><span data-ttu-id="5ee18-106">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="5ee18-106">Requirements</span></span>  
 <span data-ttu-id="5ee18-107">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ee18-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ee18-108">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5ee18-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5ee18-109">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ee18-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ee18-110">**Versione .NET Framework:** 1,0</span><span class="sxs-lookup"><span data-stu-id="5ee18-110">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ee18-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ee18-111">See also</span></span>

- [<span data-ttu-id="5ee18-112">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="5ee18-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="5ee18-113">Metodo ExceptionCLRCatcherExecute</span><span class="sxs-lookup"><span data-stu-id="5ee18-113">ExceptionCLRCatcherExecute Method</span></span>](icorprofilercallback-exceptionclrcatcherexecute-method.md)

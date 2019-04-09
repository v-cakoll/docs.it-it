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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b640a6dee9ae50278d6a844d20d21eae156e9dd7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59200961"
---
# <a name="icorprofilercallbackexceptionclrcatcherexecute-method"></a><span data-ttu-id="56f62-102">Metodo ICorProfilerCallback::ExceptionCLRCatcherExecute</span><span class="sxs-lookup"><span data-stu-id="56f62-102">ICorProfilerCallback::ExceptionCLRCatcherExecute Method</span></span>
<span data-ttu-id="56f62-103">Chiamato quando un `catch` blocca per un'eccezione viene eseguita all'interno di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="56f62-103">Called when a `catch` block for an exception is executed inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="56f62-104">Questo metodo è obsoleto in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="56f62-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56f62-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="56f62-105">Syntax</span></span>  
  
```  
HRESULT ExceptionCLRCatcherExecute();  
```  
  
## <a name="requirements"></a><span data-ttu-id="56f62-106">Requisiti</span><span class="sxs-lookup"><span data-stu-id="56f62-106">Requirements</span></span>  
 <span data-ttu-id="56f62-107">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56f62-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56f62-108">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="56f62-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="56f62-109">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="56f62-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="56f62-110">**Versioni di .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="56f62-110">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56f62-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56f62-111">See also</span></span>

- [<span data-ttu-id="56f62-112">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="56f62-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="56f62-113">Metodo ExceptionCLRCatcherFound</span><span class="sxs-lookup"><span data-stu-id="56f62-113">ExceptionCLRCatcherFound Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherfound-method.md)

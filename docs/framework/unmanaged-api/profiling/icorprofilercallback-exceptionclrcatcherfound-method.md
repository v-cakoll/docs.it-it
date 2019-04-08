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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 59225677671388b4ed31f7fa440b6e502b604c63
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59073014"
---
# <a name="icorprofilercallbackexceptionclrcatcherfound-method"></a><span data-ttu-id="edc55-102">Metodo ICorProfilerCallback::ExceptionCLRCatcherFound</span><span class="sxs-lookup"><span data-stu-id="edc55-102">ICorProfilerCallback::ExceptionCLRCatcherFound Method</span></span>
<span data-ttu-id="edc55-103">Chiamato quando un `catch` blocca per un'eccezione si trova all'interno di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="edc55-103">Called when a `catch` block for an exception is found inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="edc55-104">Questo metodo è obsoleto in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="edc55-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edc55-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="edc55-105">Syntax</span></span>  
  
```  
HRESULT ExceptionCLRCatcherFound();  
```  
  
## <a name="requirements"></a><span data-ttu-id="edc55-106">Requisiti</span><span class="sxs-lookup"><span data-stu-id="edc55-106">Requirements</span></span>  
 <span data-ttu-id="edc55-107">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="edc55-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edc55-108">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="edc55-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="edc55-109">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="edc55-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="edc55-110">**Versione di .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="edc55-110">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edc55-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="edc55-111">See also</span></span>

- [<span data-ttu-id="edc55-112">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="edc55-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="edc55-113">Metodo ExceptionCLRCatcherExecute</span><span class="sxs-lookup"><span data-stu-id="edc55-113">ExceptionCLRCatcherExecute Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherexecute-method.md)

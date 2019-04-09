---
title: Metodo ICorProfilerCallback2::ThreadNameChanged
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.ThreadNameChanged
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::ThreadNameChanged
helpviewer_keywords:
- ThreadNameChanged method [.NET Framework profiling]
- ICorProfilerCallback2::ThreadNameChanged method [.NET Framework profiling]
ms.assetid: c8bbd76d-a9ff-44f2-87a6-be052819da36
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dbd9374decdce171d45e57512470c652abc24882
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173673"
---
# <a name="icorprofilercallback2threadnamechanged-method"></a><span data-ttu-id="7a8a0-102">Metodo ICorProfilerCallback2::ThreadNameChanged</span><span class="sxs-lookup"><span data-stu-id="7a8a0-102">ICorProfilerCallback2::ThreadNameChanged Method</span></span>
<span data-ttu-id="7a8a0-103">Notifica al profiler di codice che il nome di un thread è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="7a8a0-103">Notifies the code profiler that the name of a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a8a0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7a8a0-104">Syntax</span></span>  
  
```  
HRESULT ThreadNameChanged(  
    [in] ThreadID threadId,  
    [in] ULONG cchName,  
    [in] WCHAR name[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a8a0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7a8a0-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="7a8a0-106">[in] L'ID del thread.</span><span class="sxs-lookup"><span data-stu-id="7a8a0-106">[in] The ID of the thread.</span></span>  
  
 `cchName`  
 <span data-ttu-id="7a8a0-107">[in] La lunghezza del nome del nuovo del thread.</span><span class="sxs-lookup"><span data-stu-id="7a8a0-107">[in] The length of the new name of the thread.</span></span>  
  
 `name`  
 <span data-ttu-id="7a8a0-108">[in] Il nuovo nome del thread.</span><span class="sxs-lookup"><span data-stu-id="7a8a0-108">[in] The new name of the thread.</span></span> <span data-ttu-id="7a8a0-109">Il nome non è termina con null.</span><span class="sxs-lookup"><span data-stu-id="7a8a0-109">The name is not null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a8a0-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7a8a0-110">Requirements</span></span>  
 <span data-ttu-id="7a8a0-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a8a0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a8a0-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7a8a0-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7a8a0-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a8a0-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="7a8a0-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="7a8a0-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7a8a0-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a8a0-115">See also</span></span>

- [<span data-ttu-id="7a8a0-116">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="7a8a0-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="7a8a0-117">Interfaccia ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="7a8a0-117">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)

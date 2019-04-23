---
title: Metodo ICorProfilerCallback::AssemblyLoadStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadStarted method [.NET Framework profiling]
- AssemblyLoadStarted method [.NET Framework profiling]
ms.assetid: 67e8209d-a0ca-4118-a6e6-c1ee0abc2221
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a96a2a0d6e4bc48a46850aeaadd17c2669419cef
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59219356"
---
# <a name="icorprofilercallbackassemblyloadstarted-method"></a><span data-ttu-id="da03c-102">Metodo ICorProfilerCallback::AssemblyLoadStarted</span><span class="sxs-lookup"><span data-stu-id="da03c-102">ICorProfilerCallback::AssemblyLoadStarted Method</span></span>
<span data-ttu-id="da03c-103">Notifica al profiler che un assembly viene caricato.</span><span class="sxs-lookup"><span data-stu-id="da03c-103">Notifies the profiler that an assembly is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da03c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="da03c-104">Syntax</span></span>  
  
```  
HRESULT AssemblyLoadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da03c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="da03c-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="da03c-106">[in] Identifica l'assembly in fase di caricamento.</span><span class="sxs-lookup"><span data-stu-id="da03c-106">[in] Identifies the assembly that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da03c-107">Note</span><span class="sxs-lookup"><span data-stu-id="da03c-107">Remarks</span></span>  
 <span data-ttu-id="da03c-108">Il valore di `assemblyId` non è valido per una richiesta di informazioni finché non la [AssemblyLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md) viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="da03c-108">The value of `assemblyId` is not valid for an information request until the [ICorProfilerCallback::AssemblyLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da03c-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="da03c-109">Requirements</span></span>  
 <span data-ttu-id="da03c-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da03c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da03c-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="da03c-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="da03c-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da03c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da03c-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da03c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da03c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da03c-114">See also</span></span>

- [<span data-ttu-id="da03c-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="da03c-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)

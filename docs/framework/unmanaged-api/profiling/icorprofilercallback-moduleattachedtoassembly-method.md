---
title: Metodo ICorProfilerCallback::ModuleAttachedToAssembly
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleAttachedToAssembly
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly
helpviewer_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly method [.NET Framework profiling]
- ModuleAttachedToAssembly method [.NET Framework profiling]
ms.assetid: b595798a-5d40-4cac-ab4f-911c61d2c5d2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 791827b9c4b60cb2ee963881bc8e1a6131cd00fb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59139919"
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a><span data-ttu-id="b630d-102">Metodo ICorProfilerCallback::ModuleAttachedToAssembly</span><span class="sxs-lookup"><span data-stu-id="b630d-102">ICorProfilerCallback::ModuleAttachedToAssembly Method</span></span>
<span data-ttu-id="b630d-103">Notifica al profiler che un modulo viene allegato a tale assembly.</span><span class="sxs-lookup"><span data-stu-id="b630d-103">Notifies the profiler that a module is being attached to its parent assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b630d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b630d-104">Syntax</span></span>  
  
```  
HRESULT ModuleAttachedToAssembly(  
    [in] ModuleID   moduleId,  
    [in] AssemblyID AssemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b630d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b630d-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="b630d-106">[in] L'ID del modulo in fase di collegamento.</span><span class="sxs-lookup"><span data-stu-id="b630d-106">[in] The ID of the module that is being attached.</span></span>  
  
 `AssemblyId`  
 <span data-ttu-id="b630d-107">[in] L'ID dell'assembly padre a cui è associato il modulo.</span><span class="sxs-lookup"><span data-stu-id="b630d-107">[in] The ID of the parent assembly to which the module is attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b630d-108">Note</span><span class="sxs-lookup"><span data-stu-id="b630d-108">Remarks</span></span>  
 <span data-ttu-id="b630d-109">Un modulo può essere caricato tramite una tabella di indirizzi di importazione (IAT), tramite una chiamata a `LoadLibrary`, o tramite un riferimento ai metadati.</span><span class="sxs-lookup"><span data-stu-id="b630d-109">A module can be loaded through an import address table (IAT), through a call to `LoadLibrary`, or through a metadata reference.</span></span> <span data-ttu-id="b630d-110">Di conseguenza, il caricatore di common language runtime (CLR) dispone di più percorsi di codice per determinare l'assembly in cui si trova un modulo.</span><span class="sxs-lookup"><span data-stu-id="b630d-110">As a result, the common language runtime (CLR) loader has multiple code paths for determining the assembly in which a module lives.</span></span> <span data-ttu-id="b630d-111">Pertanto, è possibile che dopo aver [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) viene chiamato, il modulo non sa quali assembly si trova in e ID dell'assembly padre non è possibile.</span><span class="sxs-lookup"><span data-stu-id="b630d-111">Therefore, it is possible that after [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) is called, the module does not know what assembly it is in and getting the parent assembly ID is not possible.</span></span> <span data-ttu-id="b630d-112">Il `ModuleAttachedToAssembly` metodo viene chiamato quando il modulo è collegato al relativo assembly padre ed è possibile ottenere l'ID di tale assembly.</span><span class="sxs-lookup"><span data-stu-id="b630d-112">The `ModuleAttachedToAssembly` method is called when the module is attached to its parent assembly and its parent assembly ID can be obtained.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b630d-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b630d-113">Requirements</span></span>  
 <span data-ttu-id="b630d-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b630d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b630d-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b630d-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b630d-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b630d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b630d-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b630d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b630d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b630d-118">See also</span></span>

- [<span data-ttu-id="b630d-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="b630d-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)

---
title: Metodo ICorProfilerCallback::ModuleAttachedToAssembly
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ModuleAttachedToAssembly
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ModuleAttachedToAssembly
helpviewer_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly method [.NET Framework profiling]
- ModuleAttachedToAssembly method [.NET Framework profiling]
ms.assetid: b595798a-5d40-4cac-ab4f-911c61d2c5d2
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2c285a42bb48970756a54d5313d2839c76a9835c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a><span data-ttu-id="3852a-102">Metodo ICorProfilerCallback::ModuleAttachedToAssembly</span><span class="sxs-lookup"><span data-stu-id="3852a-102">ICorProfilerCallback::ModuleAttachedToAssembly Method</span></span>
<span data-ttu-id="3852a-103">Notifica al profiler che un modulo viene allegato a tale assembly.</span><span class="sxs-lookup"><span data-stu-id="3852a-103">Notifies the profiler that a module is being attached to its parent assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3852a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3852a-104">Syntax</span></span>  
  
```  
HRESULT ModuleAttachedToAssembly(  
    [in] ModuleID   moduleId,  
    [in] AssemblyID AssemblyId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3852a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3852a-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="3852a-106">[in] L'ID del modulo che si sta collegando.</span><span class="sxs-lookup"><span data-stu-id="3852a-106">[in] The ID of the module that is being attached.</span></span>  
  
 `AssemblyId`  
 <span data-ttu-id="3852a-107">[in] L'ID dell'assembly padre a cui è associato il modulo.</span><span class="sxs-lookup"><span data-stu-id="3852a-107">[in] The ID of the parent assembly to which the module is attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3852a-108">Note</span><span class="sxs-lookup"><span data-stu-id="3852a-108">Remarks</span></span>  
 <span data-ttu-id="3852a-109">Un modulo può essere caricato tramite una tabella di indirizzi di importazione (IAT), tramite una chiamata a `LoadLibrary`, o tramite un riferimento ai metadati.</span><span class="sxs-lookup"><span data-stu-id="3852a-109">A module can be loaded through an import address table (IAT), through a call to `LoadLibrary`, or through a metadata reference.</span></span> <span data-ttu-id="3852a-110">Di conseguenza, il caricatore di common language runtime (CLR) dispone di più percorsi di codice per determinare l'assembly in cui si trova un modulo.</span><span class="sxs-lookup"><span data-stu-id="3852a-110">As a result, the common language runtime (CLR) loader has multiple code paths for determining the assembly in which a module lives.</span></span> <span data-ttu-id="3852a-111">Pertanto, è possibile che dopo [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) viene chiamato, il modulo non sappia quali assembly si trova e l'ID dell'assembly padre non è possibile.</span><span class="sxs-lookup"><span data-stu-id="3852a-111">Therefore, it is possible that after [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) is called, the module does not know what assembly it is in and getting the parent assembly ID is not possible.</span></span> <span data-ttu-id="3852a-112">Il `ModuleAttachedToAssembly` metodo viene chiamato quando il modulo è connesso al relativo assembly padre ed è possibile ottenere l'ID di tale assembly.</span><span class="sxs-lookup"><span data-stu-id="3852a-112">The `ModuleAttachedToAssembly` method is called when the module is attached to its parent assembly and its parent assembly ID can be obtained.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3852a-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3852a-113">Requirements</span></span>  
 <span data-ttu-id="3852a-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3852a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3852a-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3852a-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3852a-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3852a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3852a-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3852a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3852a-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3852a-118">See Also</span></span>  
 [<span data-ttu-id="3852a-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="3852a-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)

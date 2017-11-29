---
title: Metodo ICorProfilerCallback::FunctionUnloadStarted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.FunctionUnloadStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::FunctionUnloadStarted
helpviewer_keywords:
- FunctionUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::FunctionUnloadStarted method [.NET Framework profiling]
ms.assetid: d6a5fa8b-09c6-47a5-b60e-6cf2e355df30
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: efd08eedf6812a46a46135eaa6f0089257f0a209
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a><span data-ttu-id="d648a-102">Metodo ICorProfilerCallback::FunctionUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="d648a-102">ICorProfilerCallback::FunctionUnloadStarted Method</span></span>
<span data-ttu-id="d648a-103">Notifica al profiler che il runtime ha iniziato a scaricare una funzione.</span><span class="sxs-lookup"><span data-stu-id="d648a-103">Notifies the profiler that the runtime has started to unload a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d648a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d648a-104">Syntax</span></span>  
  
```  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="d648a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d648a-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="d648a-106">[in] L'ID della funzione che sta per essere scaricata.</span><span class="sxs-lookup"><span data-stu-id="d648a-106">[in] The ID of the function that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d648a-107">Note</span><span class="sxs-lookup"><span data-stu-id="d648a-107">Remarks</span></span>  
 <span data-ttu-id="d648a-108">Il valore di `functionId` parametro non è più valido dopo che questo metodo viene restituito al chiamante.</span><span class="sxs-lookup"><span data-stu-id="d648a-108">The value of the `functionId` parameter is no longer valid after this method returns to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d648a-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d648a-109">Requirements</span></span>  
 <span data-ttu-id="d648a-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d648a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d648a-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d648a-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d648a-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d648a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d648a-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d648a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d648a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d648a-114">See Also</span></span>  
 [<span data-ttu-id="d648a-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="d648a-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)

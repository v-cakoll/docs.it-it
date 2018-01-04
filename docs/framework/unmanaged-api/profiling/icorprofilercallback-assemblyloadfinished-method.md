---
title: Metodo ICorProfilerCallback::AssemblyLoadFinished
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.AssemblyLoadFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::AssemblyLoadFinished
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadFinished method [.NET Framework profiling]
- AssemblyLoadFinished method [.NET Framework profiling]
ms.assetid: 86d98f39-52e6-4c61-a625-9760f695ff12
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9de280a1b92bc921ecb400c80522f21cf65f861a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a><span data-ttu-id="cb35f-102">Metodo ICorProfilerCallback::AssemblyLoadFinished</span><span class="sxs-lookup"><span data-stu-id="cb35f-102">ICorProfilerCallback::AssemblyLoadFinished Method</span></span>
<span data-ttu-id="cb35f-103">Notifica al profiler che un assembly è stato completato il caricamento.</span><span class="sxs-lookup"><span data-stu-id="cb35f-103">Notifies the profiler that an assembly has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb35f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cb35f-104">Syntax</span></span>  
  
```  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cb35f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cb35f-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="cb35f-106">[in] Identifica l'assembly caricato.</span><span class="sxs-lookup"><span data-stu-id="cb35f-106">[in] Identifies the assembly that was loaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="cb35f-107">[in] Un valore HRESULT che indica se l'assembly è stato caricato correttamente.</span><span class="sxs-lookup"><span data-stu-id="cb35f-107">[in] An HRESULT that indicates whether the assembly finished loading successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb35f-108">Note</span><span class="sxs-lookup"><span data-stu-id="cb35f-108">Remarks</span></span>  
 <span data-ttu-id="cb35f-109">Il valore di `assemblyId` non è valido per una richiesta di informazioni fino a quando il `AssemblyLoadFinished` metodo viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="cb35f-109">The value of `assemblyId` is not valid for an information request until the `AssemblyLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="cb35f-110">Alcune parti del caricamento dell'assembly potrebbero continuare dopo il `AssemblyLoadFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="cb35f-110">Some parts of loading the assembly might continue after the `AssemblyLoadFinished` callback.</span></span> <span data-ttu-id="cb35f-111">Un HRESULT di errore in `hrStatus` indica un errore.</span><span class="sxs-lookup"><span data-stu-id="cb35f-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="cb35f-112">Tuttavia, un HRESULT positivo in `hrStatus` indica solo che la prima parte del caricamento dell'assembly ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="cb35f-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb35f-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cb35f-113">Requirements</span></span>  
 <span data-ttu-id="cb35f-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb35f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb35f-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cb35f-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cb35f-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb35f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb35f-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb35f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb35f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb35f-118">See Also</span></span>  
 [<span data-ttu-id="cb35f-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="cb35f-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)

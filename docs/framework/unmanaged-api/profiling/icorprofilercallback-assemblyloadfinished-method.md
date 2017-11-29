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
ms.openlocfilehash: af5089603c2044b10061a32c5921b9eeadf86b36
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a><span data-ttu-id="7443e-102">Metodo ICorProfilerCallback::AssemblyLoadFinished</span><span class="sxs-lookup"><span data-stu-id="7443e-102">ICorProfilerCallback::AssemblyLoadFinished Method</span></span>
<span data-ttu-id="7443e-103">Notifica al profiler che un assembly è stato completato il caricamento.</span><span class="sxs-lookup"><span data-stu-id="7443e-103">Notifies the profiler that an assembly has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7443e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7443e-104">Syntax</span></span>  
  
```  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7443e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7443e-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="7443e-106">[in] Identifica l'assembly caricato.</span><span class="sxs-lookup"><span data-stu-id="7443e-106">[in] Identifies the assembly that was loaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="7443e-107">[in] Un valore HRESULT che indica se l'assembly è stato caricato correttamente.</span><span class="sxs-lookup"><span data-stu-id="7443e-107">[in] An HRESULT that indicates whether the assembly finished loading successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7443e-108">Note</span><span class="sxs-lookup"><span data-stu-id="7443e-108">Remarks</span></span>  
 <span data-ttu-id="7443e-109">Il valore di `assemblyId` non è valido per una richiesta di informazioni fino a quando il `AssemblyLoadFinished` metodo viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="7443e-109">The value of `assemblyId` is not valid for an information request until the `AssemblyLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="7443e-110">Alcune parti del caricamento dell'assembly potrebbero continuare dopo il `AssemblyLoadFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="7443e-110">Some parts of loading the assembly might continue after the `AssemblyLoadFinished` callback.</span></span> <span data-ttu-id="7443e-111">Un HRESULT di errore in `hrStatus` indica un errore.</span><span class="sxs-lookup"><span data-stu-id="7443e-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="7443e-112">Tuttavia, un HRESULT positivo in `hrStatus` indica solo che la prima parte del caricamento dell'assembly ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7443e-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7443e-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7443e-113">Requirements</span></span>  
 <span data-ttu-id="7443e-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7443e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7443e-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7443e-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7443e-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7443e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7443e-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7443e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7443e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7443e-118">See Also</span></span>  
 [<span data-ttu-id="7443e-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="7443e-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)

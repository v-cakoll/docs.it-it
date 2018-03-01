---
title: Metodo ICorProfilerCallback::ClassLoadFinished
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback.ClassLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadFinished
helpviewer_keywords:
- ClassLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ClassLoadFinished method [.NET Framework profiling]
ms.assetid: 3dd80fbe-d62d-4d4d-acf8-5b7d0efe607e
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ae55325f514f9bec3efdf4764958e4b3fafd922b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackclassloadfinished-method"></a><span data-ttu-id="3d670-102">Metodo ICorProfilerCallback::ClassLoadFinished</span><span class="sxs-lookup"><span data-stu-id="3d670-102">ICorProfilerCallback::ClassLoadFinished Method</span></span>
<span data-ttu-id="3d670-103">Notifica al profiler che ha terminato il caricamento di una classe.</span><span class="sxs-lookup"><span data-stu-id="3d670-103">Notifies the profiler that a class has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d670-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3d670-104">Syntax</span></span>  
  
```  
HRESULT ClassLoadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3d670-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3d670-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="3d670-106">[in] Identifica la classe che è stata caricata.</span><span class="sxs-lookup"><span data-stu-id="3d670-106">[in] Identifies the class that was loaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="3d670-107">[in] Un valore HRESULT che indica se la classe sia stato caricato correttamente.</span><span class="sxs-lookup"><span data-stu-id="3d670-107">[in] An HRESULT that indicates whether the class loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d670-108">Note</span><span class="sxs-lookup"><span data-stu-id="3d670-108">Remarks</span></span>  
 <span data-ttu-id="3d670-109">Il valore di `classId` non è valido per una richiesta di informazioni fino a quando il `ClassLoadFinished` metodo viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="3d670-109">The value of `classId` is not valid for an information request until the `ClassLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="3d670-110">Alcune parti del caricamento della classe potrebbero continuare dopo il `ClassLoadFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="3d670-110">Some parts of loading the class might continue after the `ClassLoadFinished` callback.</span></span> <span data-ttu-id="3d670-111">Un HRESULT di errore in `hrStatus` indica un errore.</span><span class="sxs-lookup"><span data-stu-id="3d670-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="3d670-112">Tuttavia, un HRESULT positivo in `hrStatus` indica solo che la prima parte del caricamento della classe ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="3d670-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d670-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3d670-113">Requirements</span></span>  
 <span data-ttu-id="3d670-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d670-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d670-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3d670-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3d670-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d670-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d670-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d670-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d670-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d670-118">See Also</span></span>  
 [<span data-ttu-id="3d670-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="3d670-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="3d670-120">Metodo ClassLoadStarted</span><span class="sxs-lookup"><span data-stu-id="3d670-120">ClassLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)

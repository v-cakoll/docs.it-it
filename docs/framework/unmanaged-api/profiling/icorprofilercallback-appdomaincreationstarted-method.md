---
title: Metodo ICorProfilerCallback::AppDomainCreationStarted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.AppDomainCreationStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::AppDomainCreationStarted
helpviewer_keywords:
- AppDomainCreationStarted method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationStarted method [.NET Framework profiling]
ms.assetid: b2a8240b-07fe-4859-bb2b-7d3adbfa0a9f
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 395664081460677c4d2b94fc5478513ce239c5be
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackappdomaincreationstarted-method"></a><span data-ttu-id="8fa3b-102">Metodo ICorProfilerCallback::AppDomainCreationStarted</span><span class="sxs-lookup"><span data-stu-id="8fa3b-102">ICorProfilerCallback::AppDomainCreationStarted Method</span></span>
<span data-ttu-id="8fa3b-103">Notifica al profiler la creazione di un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="8fa3b-103">Notifies the profiler that an application domain is being created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fa3b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8fa3b-104">Syntax</span></span>  
  
```  
HRESULT AppDomainCreationStarted(  
    [in] AppDomainID appDomainId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8fa3b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8fa3b-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="8fa3b-106">[in] Identifica il dominio viene creato.</span><span class="sxs-lookup"><span data-stu-id="8fa3b-106">[in] Identifies the domain which is being created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8fa3b-107">Note</span><span class="sxs-lookup"><span data-stu-id="8fa3b-107">Remarks</span></span>  
 <span data-ttu-id="8fa3b-108">L'ID non è valido per qualsiasi richiesta di informazioni fino a quando il [ICorProfilerCallback:: AppDomainCreationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md) metodo viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="8fa3b-108">The ID is not valid for any information request until the [ICorProfilerCallback::AppDomainCreationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fa3b-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8fa3b-109">Requirements</span></span>  
 <span data-ttu-id="8fa3b-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8fa3b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fa3b-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8fa3b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8fa3b-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8fa3b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8fa3b-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fa3b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fa3b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8fa3b-114">See Also</span></span>  
 [<span data-ttu-id="8fa3b-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="8fa3b-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)

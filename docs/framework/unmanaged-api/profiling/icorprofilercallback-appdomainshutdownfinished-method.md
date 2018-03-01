---
title: Metodo ICorProfilerCallback::AppDomainShutdownFinished
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
- ICorProfilerCallback.AppDomainShutdownFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainShutdownFinished
helpviewer_keywords:
- AppDomainShutdownFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownFinished method [.NET Framework profiling]
ms.assetid: 52794819-0a59-4bb1-a265-0f158cd5cd65
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e681c64017e99eaaf0b786e48ca96b4435b08890
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a><span data-ttu-id="e8b56-102">Metodo ICorProfilerCallback::AppDomainShutdownFinished</span><span class="sxs-lookup"><span data-stu-id="e8b56-102">ICorProfilerCallback::AppDomainShutdownFinished Method</span></span>
<span data-ttu-id="e8b56-103">Notifica al profiler che un dominio applicazione è stato scaricato da un processo.</span><span class="sxs-lookup"><span data-stu-id="e8b56-103">Notifies the profiler that an application domain has been unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8b56-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8b56-104">Syntax</span></span>  
  
```  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e8b56-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e8b56-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="e8b56-106">[in] Identifica il dominio in cui sono archiviati gli assembly dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e8b56-106">[in] Identifies the domain in which the application's assemblies are stored.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="e8b56-107">[in] Un valore HRESULT che indica se il dominio applicazione è stato scaricato correttamente.</span><span class="sxs-lookup"><span data-stu-id="e8b56-107">[in] An HRESULT that indicates whether the application domain was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8b56-108">Note</span><span class="sxs-lookup"><span data-stu-id="e8b56-108">Remarks</span></span>  
 <span data-ttu-id="e8b56-109">Il valore di `appDomainId` non è valido per una richiesta di informazioni dopo il [AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) metodo restituisce.</span><span class="sxs-lookup"><span data-stu-id="e8b56-109">The value of `appDomainId` is not valid for an information request after the [ICorProfilerCallback::AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="e8b56-110">Alcune parti dello scaricamento del dominio applicazione potrebbero continuare dopo il `AppDomainCreationFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="e8b56-110">Some parts of unloading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="e8b56-111">Un HRESULT di errore in `hrStatus` indica un errore.</span><span class="sxs-lookup"><span data-stu-id="e8b56-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="e8b56-112">Tuttavia, un HRESULT positivo in `hrStatus` indica solo che la prima parte dello scaricamento del dominio applicazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="e8b56-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8b56-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e8b56-113">Requirements</span></span>  
 <span data-ttu-id="e8b56-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8b56-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8b56-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e8b56-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e8b56-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8b56-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8b56-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8b56-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8b56-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8b56-118">See Also</span></span>  
 [<span data-ttu-id="e8b56-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="e8b56-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)

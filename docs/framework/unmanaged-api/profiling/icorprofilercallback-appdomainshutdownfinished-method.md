---
title: Metodo ICorProfilerCallback::AppDomainShutdownFinished
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c89a7671cde9e519d0fc66751ee8f95b34fe9039
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54669666"
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a><span data-ttu-id="e3dcd-102">Metodo ICorProfilerCallback::AppDomainShutdownFinished</span><span class="sxs-lookup"><span data-stu-id="e3dcd-102">ICorProfilerCallback::AppDomainShutdownFinished Method</span></span>
<span data-ttu-id="e3dcd-103">Notifica al profiler che un dominio dell'applicazione è stato scaricato da un processo.</span><span class="sxs-lookup"><span data-stu-id="e3dcd-103">Notifies the profiler that an application domain has been unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3dcd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e3dcd-104">Syntax</span></span>  
  
```  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e3dcd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e3dcd-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="e3dcd-106">[in] Identifica il dominio in cui sono archiviati gli assembly dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e3dcd-106">[in] Identifies the domain in which the application's assemblies are stored.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="e3dcd-107">[in] HRESULT che indica se il dominio dell'applicazione è stato scaricato correttamente.</span><span class="sxs-lookup"><span data-stu-id="e3dcd-107">[in] An HRESULT that indicates whether the application domain was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e3dcd-108">Note</span><span class="sxs-lookup"><span data-stu-id="e3dcd-108">Remarks</span></span>  
 <span data-ttu-id="e3dcd-109">Il valore di `appDomainId` non è valido per una richiesta di informazioni dopo che il [AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) restituzione del metodo.</span><span class="sxs-lookup"><span data-stu-id="e3dcd-109">The value of `appDomainId` is not valid for an information request after the [ICorProfilerCallback::AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="e3dcd-110">Alcune parti dello scaricamento del dominio dell'applicazione potrebbero continuare dopo il `AppDomainCreationFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="e3dcd-110">Some parts of unloading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="e3dcd-111">Un HRESULT di errore in `hrStatus` indica un errore.</span><span class="sxs-lookup"><span data-stu-id="e3dcd-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="e3dcd-112">Tuttavia, un HRESULT di esito positivo in `hrStatus` indica solo che la prima parte dello scaricamento del dominio applicazione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="e3dcd-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3dcd-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e3dcd-113">Requirements</span></span>  
 <span data-ttu-id="e3dcd-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3dcd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3dcd-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e3dcd-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e3dcd-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3dcd-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3dcd-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3dcd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3dcd-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3dcd-118">See also</span></span>
- [<span data-ttu-id="e3dcd-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="e3dcd-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)

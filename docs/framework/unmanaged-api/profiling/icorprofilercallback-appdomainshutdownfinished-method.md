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
ms.openlocfilehash: 8ff7d5a593388bd3a584e031aea411dfdb6c9845
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445202"
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a><span data-ttu-id="5aa89-102">Metodo ICorProfilerCallback::AppDomainShutdownFinished</span><span class="sxs-lookup"><span data-stu-id="5aa89-102">ICorProfilerCallback::AppDomainShutdownFinished Method</span></span>
<span data-ttu-id="5aa89-103">Notifies the profiler that an application domain has been unloaded from a process.</span><span class="sxs-lookup"><span data-stu-id="5aa89-103">Notifies the profiler that an application domain has been unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5aa89-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5aa89-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5aa89-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5aa89-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="5aa89-106">[in] Identifies the domain in which the application's assemblies are stored.</span><span class="sxs-lookup"><span data-stu-id="5aa89-106">[in] Identifies the domain in which the application's assemblies are stored.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="5aa89-107">[in] An HRESULT that indicates whether the application domain was unloaded successfully.</span><span class="sxs-lookup"><span data-stu-id="5aa89-107">[in] An HRESULT that indicates whether the application domain was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5aa89-108">Note</span><span class="sxs-lookup"><span data-stu-id="5aa89-108">Remarks</span></span>  
 <span data-ttu-id="5aa89-109">The value of `appDomainId` is not valid for an information request after the [ICorProfilerCallback::AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) method returns.</span><span class="sxs-lookup"><span data-stu-id="5aa89-109">The value of `appDomainId` is not valid for an information request after the [ICorProfilerCallback::AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="5aa89-110">Some parts of unloading the application domain might continue after the `AppDomainCreationFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="5aa89-110">Some parts of unloading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="5aa89-111">A failure HRESULT in `hrStatus` indicates a failure.</span><span class="sxs-lookup"><span data-stu-id="5aa89-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="5aa89-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the application domain has succeeded.</span><span class="sxs-lookup"><span data-stu-id="5aa89-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5aa89-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5aa89-113">Requirements</span></span>  
 <span data-ttu-id="5aa89-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5aa89-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5aa89-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5aa89-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5aa89-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5aa89-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5aa89-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5aa89-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5aa89-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5aa89-118">See also</span></span>

- [<span data-ttu-id="5aa89-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="5aa89-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)

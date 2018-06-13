---
title: Metodo ICorProfilerCallback::AppDomainShutdownStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainShutdownStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainShutdownStarted
helpviewer_keywords:
- AppDomainShutdownStarted method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownStarted method [.NET Framework profiling]
ms.assetid: d23a3408-b525-4aec-a186-2ac7ca65d7a4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fd1e5daada8793e94980afc5f0cf509915bd288e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450929"
---
# <a name="icorprofilercallbackappdomainshutdownstarted-method"></a><span data-ttu-id="a787e-102">Metodo ICorProfilerCallback::AppDomainShutdownStarted</span><span class="sxs-lookup"><span data-stu-id="a787e-102">ICorProfilerCallback::AppDomainShutdownStarted Method</span></span>
<span data-ttu-id="a787e-103">Notifica al profiler che un dominio applicazione è in corso lo scaricamento da un processo.</span><span class="sxs-lookup"><span data-stu-id="a787e-103">Notifies the profiler that an application domain is being unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a787e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a787e-104">Syntax</span></span>  
  
```  
HRESULT AppDomainShutdownStarted(  
    [in] AppDomainID appDomainId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a787e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a787e-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="a787e-106">[in] Identifica il dominio in cui sono archiviati gli assembly dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a787e-106">[in] Identifies the domain in which the application's assemblies are stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a787e-107">Note</span><span class="sxs-lookup"><span data-stu-id="a787e-107">Remarks</span></span>  
 <span data-ttu-id="a787e-108">Il valore di `appDomainId` non è valida per qualsiasi richiesta di informazioni dopo il `AppDomainShutdownStarted` metodo restituisce, si tratta di completamento per ottenere informazioni su questo dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="a787e-108">The value of `appDomainId` is not valid for any information request after the `AppDomainShutdownStarted` method returns — this is the profiler's last chance to get information about this application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a787e-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a787e-109">Requirements</span></span>  
 <span data-ttu-id="a787e-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a787e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a787e-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a787e-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a787e-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="a787e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a787e-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a787e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a787e-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a787e-114">See Also</span></span>  
 [<span data-ttu-id="a787e-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="a787e-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)

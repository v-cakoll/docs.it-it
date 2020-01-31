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
ms.openlocfilehash: d280b008b34befce04159d02dfbb3de37b262c3c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866663"
---
# <a name="icorprofilercallbackappdomainshutdownstarted-method"></a><span data-ttu-id="09339-102">Metodo ICorProfilerCallback::AppDomainShutdownStarted</span><span class="sxs-lookup"><span data-stu-id="09339-102">ICorProfilerCallback::AppDomainShutdownStarted Method</span></span>
<span data-ttu-id="09339-103">Notifica al profiler che un dominio applicazione viene scaricato da un processo.</span><span class="sxs-lookup"><span data-stu-id="09339-103">Notifies the profiler that an application domain is being unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09339-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="09339-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09339-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="09339-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="09339-106">\[in] identifica il dominio in cui sono archiviati gli assembly dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="09339-106">\[in] Identifies the domain in which the application's assemblies are stored.</span></span>

## <a name="remarks"></a><span data-ttu-id="09339-107">Note</span><span class="sxs-lookup"><span data-stu-id="09339-107">Remarks</span></span>  
 <span data-ttu-id="09339-108">Il valore di `appDomainId` non è valido per tutte le richieste di informazioni dopo la restituzione del metodo `AppDomainShutdownStarted`, ovvero l'ultima possibilità del profiler di ottenere informazioni sul dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="09339-108">The value of `appDomainId` is not valid for any information request after the `AppDomainShutdownStarted` method returns — this is the profiler's last chance to get information about this application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09339-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="09339-109">Requirements</span></span>  
 <span data-ttu-id="09339-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09339-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09339-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="09339-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="09339-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09339-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09339-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09339-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09339-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09339-114">See also</span></span>

- [<span data-ttu-id="09339-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="09339-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)

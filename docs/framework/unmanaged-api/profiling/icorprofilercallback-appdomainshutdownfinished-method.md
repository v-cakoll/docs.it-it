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
ms.openlocfilehash: 722a1e0adea41a13ca25829c53372c29187b80bd
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500468"
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a><span data-ttu-id="d52b7-102">Metodo ICorProfilerCallback::AppDomainShutdownFinished</span><span class="sxs-lookup"><span data-stu-id="d52b7-102">ICorProfilerCallback::AppDomainShutdownFinished Method</span></span>
<span data-ttu-id="d52b7-103">Notifica al profiler che un dominio applicazione è stato scaricato da un processo.</span><span class="sxs-lookup"><span data-stu-id="d52b7-103">Notifies the profiler that an application domain has been unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d52b7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d52b7-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d52b7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d52b7-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="d52b7-106">\[in] identifica il dominio in cui sono archiviati gli assembly dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d52b7-106">\[in] Identifies the domain in which the application's assemblies are stored.</span></span>

- `hrStatus`

  <span data-ttu-id="d52b7-107">\[in] valore HRESULT che indica se il dominio applicazione è stato scaricato correttamente.</span><span class="sxs-lookup"><span data-stu-id="d52b7-107">\[in] An HRESULT that indicates whether the application domain was unloaded successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="d52b7-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d52b7-108">Remarks</span></span>  
 <span data-ttu-id="d52b7-109">Il valore di `appDomainId` non è valido per una richiesta di informazioni dopo che il metodo [ICorProfilerCallback:: AppDomainShutdownStarted](icorprofilercallback-appdomainshutdownstarted-method.md) restituisce.</span><span class="sxs-lookup"><span data-stu-id="d52b7-109">The value of `appDomainId` is not valid for an information request after the [ICorProfilerCallback::AppDomainShutdownStarted](icorprofilercallback-appdomainshutdownstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="d52b7-110">Alcune parti dello scaricamento del dominio dell'applicazione potrebbero continuare dopo il `AppDomainCreationFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="d52b7-110">Some parts of unloading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="d52b7-111">Un errore HRESULT in `hrStatus` indica un errore.</span><span class="sxs-lookup"><span data-stu-id="d52b7-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="d52b7-112">Tuttavia, un HRESULT con esito positivo in `hrStatus` indica solo che la prima parte dello scaricamento del dominio applicazione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="d52b7-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d52b7-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d52b7-113">Requirements</span></span>  
 <span data-ttu-id="d52b7-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d52b7-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d52b7-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d52b7-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d52b7-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d52b7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d52b7-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d52b7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d52b7-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d52b7-118">See also</span></span>

- [<span data-ttu-id="d52b7-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="d52b7-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)

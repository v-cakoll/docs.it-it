---
title: Metodo ICorProfilerCallback::AppDomainCreationStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainCreationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainCreationStarted
helpviewer_keywords:
- AppDomainCreationStarted method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationStarted method [.NET Framework profiling]
ms.assetid: b2a8240b-07fe-4859-bb2b-7d3adbfa0a9f
topic_type:
- apiref
ms.openlocfilehash: fcebe65b7f39dd2849946e445a694ad5e9b1a65d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500481"
---
# <a name="icorprofilercallbackappdomaincreationstarted-method"></a><span data-ttu-id="6eae6-102">Metodo ICorProfilerCallback::AppDomainCreationStarted</span><span class="sxs-lookup"><span data-stu-id="6eae6-102">ICorProfilerCallback::AppDomainCreationStarted Method</span></span>
<span data-ttu-id="6eae6-103">Notifica al profiler che è in corso la creazione di un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="6eae6-103">Notifies the profiler that an application domain is being created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6eae6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6eae6-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainCreationStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6eae6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6eae6-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="6eae6-106">\[in] identifica il dominio in fase di creazione.</span><span class="sxs-lookup"><span data-stu-id="6eae6-106">\[in] Identifies the domain which is being created.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="6eae6-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6eae6-107">Remarks</span></span>  
 <span data-ttu-id="6eae6-108">L'ID non è valido per tutte le richieste di informazioni fino a quando non viene chiamato il metodo [ICorProfilerCallback:: AppDomainCreationFinished](icorprofilercallback-appdomaincreationfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="6eae6-108">The ID is not valid for any information request until the [ICorProfilerCallback::AppDomainCreationFinished](icorprofilercallback-appdomaincreationfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6eae6-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6eae6-109">Requirements</span></span>  
 <span data-ttu-id="6eae6-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6eae6-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6eae6-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6eae6-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6eae6-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6eae6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6eae6-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6eae6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6eae6-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6eae6-114">See also</span></span>

- [<span data-ttu-id="6eae6-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="6eae6-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)

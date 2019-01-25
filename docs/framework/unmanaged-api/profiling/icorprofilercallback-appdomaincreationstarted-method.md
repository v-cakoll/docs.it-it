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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 98fac8630403107f96f2fa86e5bcc9b0e60d0d08
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737163"
---
# <a name="icorprofilercallbackappdomaincreationstarted-method"></a><span data-ttu-id="954d1-102">Metodo ICorProfilerCallback::AppDomainCreationStarted</span><span class="sxs-lookup"><span data-stu-id="954d1-102">ICorProfilerCallback::AppDomainCreationStarted Method</span></span>
<span data-ttu-id="954d1-103">Notifica al profiler che un dominio dell'applicazione viene creato.</span><span class="sxs-lookup"><span data-stu-id="954d1-103">Notifies the profiler that an application domain is being created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="954d1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="954d1-104">Syntax</span></span>  
  
```  
HRESULT AppDomainCreationStarted(  
    [in] AppDomainID appDomainId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="954d1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="954d1-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="954d1-106">[in] Identifica il dominio di cui viene creato.</span><span class="sxs-lookup"><span data-stu-id="954d1-106">[in] Identifies the domain which is being created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="954d1-107">Note</span><span class="sxs-lookup"><span data-stu-id="954d1-107">Remarks</span></span>  
 <span data-ttu-id="954d1-108">L'ID non è valida per qualsiasi richiesta di informazioni finché il [AppDomainCreationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md) viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="954d1-108">The ID is not valid for any information request until the [ICorProfilerCallback::AppDomainCreationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="954d1-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="954d1-109">Requirements</span></span>  
 <span data-ttu-id="954d1-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="954d1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="954d1-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="954d1-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="954d1-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="954d1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="954d1-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="954d1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="954d1-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="954d1-114">See also</span></span>
- [<span data-ttu-id="954d1-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="954d1-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)

---
title: Metodo ICorProfilerCallback::AppDomainCreationFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainCreationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainCreationFinished
helpviewer_keywords:
- AppDomainCreationFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationFinished method [.NET Framework profiling]
ms.assetid: dbab7d90-d515-4dc9-8195-294d5d04bab6
topic_type:
- apiref
ms.openlocfilehash: 76f56971223154d3ed966c272081049adf30de54
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500494"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a><span data-ttu-id="eb531-102">Metodo ICorProfilerCallback::AppDomainCreationFinished</span><span class="sxs-lookup"><span data-stu-id="eb531-102">ICorProfilerCallback::AppDomainCreationFinished Method</span></span>
<span data-ttu-id="eb531-103">Notifica al profiler che è stato creato un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="eb531-103">Notifies the profiler that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb531-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eb531-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);
```  
  
## <a name="parameters"></a><span data-ttu-id="eb531-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="eb531-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="eb531-106">\[in] identifica il dominio che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="eb531-106">\[in] Identifies the domain which has been created.</span></span>

- `hrStatus`

  <span data-ttu-id="eb531-107">\[in] valore HRESULT che indica se la creazione del dominio dell'applicazione è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="eb531-107">\[in] An HRESULT that indicates whether creation of the application domain completed successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="eb531-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="eb531-108">Remarks</span></span>  
 <span data-ttu-id="eb531-109">L'ID applicazione non è valido per tutte le richieste di informazioni fino a quando non `AppDomainCreationFinished` viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="eb531-109">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span></span>  
  
 <span data-ttu-id="eb531-110">Alcune parti del caricamento del dominio dell'applicazione potrebbero continuare dopo il `AppDomainCreationFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="eb531-110">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="eb531-111">Un errore HRESULT in `hrStatus` indica un errore.</span><span class="sxs-lookup"><span data-stu-id="eb531-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="eb531-112">Tuttavia, un HRESULT con esito positivo in `hrStatus` indica solo che la prima parte della creazione del dominio dell'applicazione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="eb531-112">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb531-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="eb531-113">Requirements</span></span>  
 <span data-ttu-id="eb531-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb531-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb531-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="eb531-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="eb531-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb531-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb531-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb531-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb531-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb531-118">See also</span></span>

- [<span data-ttu-id="eb531-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="eb531-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)

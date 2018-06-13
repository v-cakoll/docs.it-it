---
title: Metodo ICorProfilerCallback::AssemblyUnloadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadFinished
helpviewer_keywords:
- AssemblyUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::AssemblyUnloadFinished method [.NET Framework profiling]
ms.assetid: 53fca564-84b1-44d4-9e21-17a492d2aae7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0d757a0455992bc82ead922a5fbf4c71f11a9085
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450869"
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a><span data-ttu-id="056dd-102">Metodo ICorProfilerCallback::AssemblyUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="056dd-102">ICorProfilerCallback::AssemblyUnloadFinished Method</span></span>
<span data-ttu-id="056dd-103">Notifica al profiler che un assembly è stato scaricato.</span><span class="sxs-lookup"><span data-stu-id="056dd-103">Notifies the profiler that an assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="056dd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="056dd-104">Syntax</span></span>  
  
```  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="056dd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="056dd-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="056dd-106">[in] Identifica l'assembly in fase di scaricamento.</span><span class="sxs-lookup"><span data-stu-id="056dd-106">[in] Identifies the assembly that is being unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="056dd-107">[in] Un valore HRESULT che indica se l'assembly è stato scaricato correttamente.</span><span class="sxs-lookup"><span data-stu-id="056dd-107">[in] An HRESULT that indicates whether the assembly was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="056dd-108">Note</span><span class="sxs-lookup"><span data-stu-id="056dd-108">Remarks</span></span>  
 <span data-ttu-id="056dd-109">Il valore di `assemblyId` non è valido per una richiesta di informazioni dopo il [ICorProfilerCallback:: AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) metodo restituisce.</span><span class="sxs-lookup"><span data-stu-id="056dd-109">The value of `assemblyId` is not valid for an information request after the [ICorProfilerCallback::AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="056dd-110">Alcune parti di scaricamento dell'assembly potrebbero continuare dopo il `AssemblyUnloadFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="056dd-110">Some parts of unloading the assembly might continue after the `AssemblyUnloadFinished` callback.</span></span> <span data-ttu-id="056dd-111">Un HRESULT di errore in `hrStatus` indica un errore.</span><span class="sxs-lookup"><span data-stu-id="056dd-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="056dd-112">Tuttavia, un HRESULT positivo in `hrStatus` indica solo che la prima parte dello scaricamento dell'assembly ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="056dd-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="056dd-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="056dd-113">Requirements</span></span>  
 <span data-ttu-id="056dd-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="056dd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="056dd-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="056dd-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="056dd-116">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="056dd-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="056dd-117">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="056dd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="056dd-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="056dd-118">See Also</span></span>  
 [<span data-ttu-id="056dd-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="056dd-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)

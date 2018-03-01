---
title: Metodo ICorProfilerCallback::COMClassicVTableDestroyed
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
- ICorProfilerCallback.COMClassicVTableDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::COMClassicVTableDestroyed
helpviewer_keywords:
- ICorProfilerCallback::COMClassicVTableDestroyed method [.NET Framework profiling]
- COMClassicVTableDestroyed method [.NET Framework profiling]
ms.assetid: 29da20ca-bf39-4356-8099-d9c3ac3423a9
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 74ee3f0ca092710342b48b8adbaa5f5cf7e8b980
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackcomclassicvtabledestroyed-method"></a><span data-ttu-id="1f49a-102">Metodo ICorProfilerCallback::COMClassicVTableDestroyed</span><span class="sxs-lookup"><span data-stu-id="1f49a-102">ICorProfilerCallback::COMClassicVTableDestroyed Method</span></span>
<span data-ttu-id="1f49a-103">Notifica al profiler che è in corso l'eliminazione di un oggetto vtable di interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="1f49a-103">Notifies the profiler that a COM interop vtable is being destroyed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1f49a-104">Questo callback è probabile mai, perché la distruzione di vtable si verifica molto vicino a arresto.</span><span class="sxs-lookup"><span data-stu-id="1f49a-104">This callback is likely never to occur, because the destruction of vtables occurs very close to shutdown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f49a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1f49a-105">Syntax</span></span>  
  
```  
HRESULT COMClassicVTableDestroyed(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1f49a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="1f49a-106">Parameters</span></span>  
 `wrappedClasId`  
 <span data-ttu-id="1f49a-107">[in] L'ID della classe per cui è stato creato l'oggetto vtable.</span><span class="sxs-lookup"><span data-stu-id="1f49a-107">[in] The ID of the class for which this vtable was created.</span></span>  
  
 `implementedIID`  
 <span data-ttu-id="1f49a-108">[in] L'ID dell'interfaccia implementata dalla classe.</span><span class="sxs-lookup"><span data-stu-id="1f49a-108">[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="1f49a-109">Questo valore può essere NULL se l'interfaccia è solo interno.</span><span class="sxs-lookup"><span data-stu-id="1f49a-109">This value may be NULL if the interface is internal only.</span></span>  
  
 `pVTable`  
 <span data-ttu-id="1f49a-110">[in] Un puntatore all'inizio dell'oggetto vtable.</span><span class="sxs-lookup"><span data-stu-id="1f49a-110">[in] A pointer to the start of the vtable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f49a-111">Note</span><span class="sxs-lookup"><span data-stu-id="1f49a-111">Remarks</span></span>  
 <span data-ttu-id="1f49a-112">Il profiler non deve bloccare nella sua implementazione di questo metodo perché lo stack potrebbe non essere in uno stato che consente operazioni di garbage collection e pertanto non può essere attivata preemptive operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="1f49a-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="1f49a-113">Se il profiler qui si blocca e viene eseguito un tentativo di operazione di garbage collection, il runtime si bloccherà finché non restituisce questo callback.</span><span class="sxs-lookup"><span data-stu-id="1f49a-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="1f49a-114">Implementazione del profiler di questo metodo non è necessario chiamare codice gestito o causare in alcun modo un'allocazione di memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="1f49a-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f49a-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1f49a-115">Requirements</span></span>  
 <span data-ttu-id="1f49a-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f49a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f49a-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1f49a-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1f49a-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f49a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f49a-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f49a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f49a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f49a-120">See Also</span></span>  
 [<span data-ttu-id="1f49a-121">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="1f49a-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="1f49a-122">Metodo COMClassicVTableCreated</span><span class="sxs-lookup"><span data-stu-id="1f49a-122">COMClassicVTableCreated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtablecreated-method.md)

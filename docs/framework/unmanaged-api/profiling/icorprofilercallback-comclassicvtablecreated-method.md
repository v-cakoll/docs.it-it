---
title: Metodo ICorProfilerCallback::COMClassicVTableCreated
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
- ICorProfilerCallback.COMClassicVTableCreated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::COMClassicVTableCreated
helpviewer_keywords:
- COMClassicVTableCreated method [.NET Framework profiling]
- ICorProfilerCallback::COMClassicVTableCreated method [.NET Framework profiling]
ms.assetid: 6e1834ab-c359-498a-b10b-984ae23cdda4
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 43fb447393e1d34ca53fbb62ecdc456a97452bc4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackcomclassicvtablecreated-method"></a><span data-ttu-id="d3134-102">Metodo ICorProfilerCallback::COMClassicVTableCreated</span><span class="sxs-lookup"><span data-stu-id="d3134-102">ICorProfilerCallback::COMClassicVTableCreated Method</span></span>
<span data-ttu-id="d3134-103">Notifica al profiler che è stato creato un oggetto vtable di interoperabilità COM per l'IID e la classe specificata.</span><span class="sxs-lookup"><span data-stu-id="d3134-103">Notifies the profiler that a COM interop vtable for the specified IID and class has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3134-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d3134-104">Syntax</span></span>  
  
```  
HRESULT COMClassicVTableCreated(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable,  
    [in] ULONG   cSlots);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d3134-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d3134-105">Parameters</span></span>  
 `wrappedClasId`  
 <span data-ttu-id="d3134-106">[in] L'ID della classe per cui è stata creata il vtable.</span><span class="sxs-lookup"><span data-stu-id="d3134-106">[in] The ID of the class for which the vtable has been created.</span></span>  
  
 `implementedIID`  
 <span data-ttu-id="d3134-107">[in] L'ID dell'interfaccia implementata dalla classe.</span><span class="sxs-lookup"><span data-stu-id="d3134-107">[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="d3134-108">Questo valore può essere NULL se l'interfaccia è solo interno.</span><span class="sxs-lookup"><span data-stu-id="d3134-108">This value may be NULL if the interface is internal only.</span></span>  
  
 `pVTable`  
 <span data-ttu-id="d3134-109">[in] Un puntatore all'inizio dell'oggetto vtable.</span><span class="sxs-lookup"><span data-stu-id="d3134-109">[in] A pointer to the start of the vtable.</span></span>  
  
 `cSlots`  
 <span data-ttu-id="d3134-110">[in] Il numero di slot in vtable.</span><span class="sxs-lookup"><span data-stu-id="d3134-110">[in] The number of slots that are in the vtable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3134-111">Note</span><span class="sxs-lookup"><span data-stu-id="d3134-111">Remarks</span></span>  
 <span data-ttu-id="d3134-112">Il profiler non deve bloccare nella sua implementazione di questo metodo perché lo stack potrebbe non essere in uno stato che consente operazioni di garbage collection e pertanto non può essere attivata preemptive operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="d3134-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="d3134-113">Se il profiler qui si blocca e viene eseguito un tentativo di operazione di garbage collection, il runtime si bloccherà finché non restituisce questo callback.</span><span class="sxs-lookup"><span data-stu-id="d3134-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="d3134-114">Implementazione del profiler di questo metodo non è necessario chiamare codice gestito o causare in alcun modo un'allocazione di memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="d3134-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3134-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d3134-115">Requirements</span></span>  
 <span data-ttu-id="d3134-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3134-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3134-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d3134-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d3134-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3134-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d3134-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3134-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3134-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3134-120">See Also</span></span>  
 [<span data-ttu-id="d3134-121">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="d3134-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="d3134-122">Metodo COMClassicVTableDestroyed</span><span class="sxs-lookup"><span data-stu-id="d3134-122">COMClassicVTableDestroyed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtabledestroyed-method.md)

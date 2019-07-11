---
title: Metodo ICorProfilerCallback::COMClassicVTableCreated
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 062b63776264ae553039a2db0fc99d4fb7bec476
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745333"
---
# <a name="icorprofilercallbackcomclassicvtablecreated-method"></a><span data-ttu-id="519b6-102">Metodo ICorProfilerCallback::COMClassicVTableCreated</span><span class="sxs-lookup"><span data-stu-id="519b6-102">ICorProfilerCallback::COMClassicVTableCreated Method</span></span>
<span data-ttu-id="519b6-103">Notifica al profiler che è stato creato un oggetto vtable interoperabilità COM per l'IID e la classe specificata.</span><span class="sxs-lookup"><span data-stu-id="519b6-103">Notifies the profiler that a COM interop vtable for the specified IID and class has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="519b6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="519b6-104">Syntax</span></span>  
  
```cpp  
HRESULT COMClassicVTableCreated(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable,  
    [in] ULONG   cSlots);  
```  
  
## <a name="parameters"></a><span data-ttu-id="519b6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="519b6-105">Parameters</span></span>  
 `wrappedClasId`  
 <span data-ttu-id="519b6-106">[in] L'ID della classe per cui è stata creata la vtable.</span><span class="sxs-lookup"><span data-stu-id="519b6-106">[in] The ID of the class for which the vtable has been created.</span></span>  
  
 `implementedIID`  
 <span data-ttu-id="519b6-107">[in] L'ID dell'interfaccia implementata dalla classe.</span><span class="sxs-lookup"><span data-stu-id="519b6-107">[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="519b6-108">Questo valore può essere NULL se l'interfaccia è solo interno.</span><span class="sxs-lookup"><span data-stu-id="519b6-108">This value may be NULL if the interface is internal only.</span></span>  
  
 `pVTable`  
 <span data-ttu-id="519b6-109">[in] Un puntatore all'inizio della vtable.</span><span class="sxs-lookup"><span data-stu-id="519b6-109">[in] A pointer to the start of the vtable.</span></span>  
  
 `cSlots`  
 <span data-ttu-id="519b6-110">[in] Il numero di slot in vtable.</span><span class="sxs-lookup"><span data-stu-id="519b6-110">[in] The number of slots that are in the vtable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="519b6-111">Note</span><span class="sxs-lookup"><span data-stu-id="519b6-111">Remarks</span></span>  
 <span data-ttu-id="519b6-112">Il profiler non deve bloccare nella propria implementazione di questo metodo perché lo stack potrebbe non essere in uno stato che consente operazioni di garbage collection e pertanto non è possibile abilitare preemptive operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="519b6-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="519b6-113">Se il profiler si blocca qui e viene tentata la garbage collection, il runtime si bloccherà fino a quando non viene restituito questo callback.</span><span class="sxs-lookup"><span data-stu-id="519b6-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="519b6-114">Implementazione del profiler di questo metodo non deve chiamare codice gestito o in qualsiasi modo causa un'allocazione di memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="519b6-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="519b6-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="519b6-115">Requirements</span></span>  
 <span data-ttu-id="519b6-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="519b6-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="519b6-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="519b6-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="519b6-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="519b6-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="519b6-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="519b6-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="519b6-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="519b6-120">See also</span></span>

- [<span data-ttu-id="519b6-121">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="519b6-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="519b6-122">Metodo COMClassicVTableDestroyed</span><span class="sxs-lookup"><span data-stu-id="519b6-122">COMClassicVTableDestroyed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtabledestroyed-method.md)

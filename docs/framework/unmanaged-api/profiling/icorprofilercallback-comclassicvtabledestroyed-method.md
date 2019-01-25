---
title: Metodo ICorProfilerCallback::COMClassicVTableDestroyed
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f60c4373410c46c5d1ea284b2cacd4b5c070ed9d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54682823"
---
# <a name="icorprofilercallbackcomclassicvtabledestroyed-method"></a><span data-ttu-id="f6047-102">Metodo ICorProfilerCallback::COMClassicVTableDestroyed</span><span class="sxs-lookup"><span data-stu-id="f6047-102">ICorProfilerCallback::COMClassicVTableDestroyed Method</span></span>
<span data-ttu-id="f6047-103">Notifica al profiler che è in corso l'eliminazione di un oggetto vtable di interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="f6047-103">Notifies the profiler that a COM interop vtable is being destroyed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6047-104">Questo callback è probabilmente mai verificarsi, perché la distruzione di vtable si verifica molto vicino di arresto.</span><span class="sxs-lookup"><span data-stu-id="f6047-104">This callback is likely never to occur, because the destruction of vtables occurs very close to shutdown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6047-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f6047-105">Syntax</span></span>  
  
```  
HRESULT COMClassicVTableDestroyed(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f6047-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f6047-106">Parameters</span></span>  
 `wrappedClasId`  
 <span data-ttu-id="f6047-107">[in] L'ID della classe per cui è stato creato questo vtable.</span><span class="sxs-lookup"><span data-stu-id="f6047-107">[in] The ID of the class for which this vtable was created.</span></span>  
  
 `implementedIID`  
 <span data-ttu-id="f6047-108">[in] L'ID dell'interfaccia implementata dalla classe.</span><span class="sxs-lookup"><span data-stu-id="f6047-108">[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="f6047-109">Questo valore può essere NULL se l'interfaccia è solo interno.</span><span class="sxs-lookup"><span data-stu-id="f6047-109">This value may be NULL if the interface is internal only.</span></span>  
  
 `pVTable`  
 <span data-ttu-id="f6047-110">[in] Un puntatore all'inizio della vtable.</span><span class="sxs-lookup"><span data-stu-id="f6047-110">[in] A pointer to the start of the vtable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6047-111">Note</span><span class="sxs-lookup"><span data-stu-id="f6047-111">Remarks</span></span>  
 <span data-ttu-id="f6047-112">Il profiler non deve bloccare nella propria implementazione di questo metodo perché lo stack potrebbe non essere in uno stato che consente operazioni di garbage collection e pertanto non è possibile abilitare preemptive operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="f6047-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="f6047-113">Se il profiler si blocca qui e viene tentata la garbage collection, il runtime si bloccherà fino a quando non viene restituito questo callback.</span><span class="sxs-lookup"><span data-stu-id="f6047-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="f6047-114">Implementazione del profiler di questo metodo non deve chiamare codice gestito o in qualsiasi modo causa un'allocazione di memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="f6047-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6047-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f6047-115">Requirements</span></span>  
 <span data-ttu-id="f6047-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6047-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6047-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f6047-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f6047-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6047-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6047-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6047-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6047-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6047-120">See also</span></span>
- [<span data-ttu-id="f6047-121">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="f6047-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="f6047-122">Metodo COMClassicVTableCreated</span><span class="sxs-lookup"><span data-stu-id="f6047-122">COMClassicVTableCreated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtablecreated-method.md)

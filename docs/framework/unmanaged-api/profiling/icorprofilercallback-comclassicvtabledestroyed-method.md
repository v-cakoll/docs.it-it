---
title: Metodo ICorProfilerCallback::COMClassicVTableDestroyed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.COMClassicVTableDestroyed
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::COMClassicVTableDestroyed
helpviewer_keywords:
- ICorProfilerCallback::COMClassicVTableDestroyed method [.NET Framework profiling]
- COMClassicVTableDestroyed method [.NET Framework profiling]
ms.assetid: 29da20ca-bf39-4356-8099-d9c3ac3423a9
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ebff8297a708b130a0d3983fd75b76c3aeaeceaf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackcomclassicvtabledestroyed-method"></a><span data-ttu-id="bee59-102">Metodo ICorProfilerCallback::COMClassicVTableDestroyed</span><span class="sxs-lookup"><span data-stu-id="bee59-102">ICorProfilerCallback::COMClassicVTableDestroyed Method</span></span>
<span data-ttu-id="bee59-103">Notifica al profiler che è in corso l'eliminazione di un oggetto vtable di interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="bee59-103">Notifies the profiler that a COM interop vtable is being destroyed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bee59-104">Questo callback è probabile mai, perché la distruzione di vtable si verifica molto vicino a arresto.</span><span class="sxs-lookup"><span data-stu-id="bee59-104">This callback is likely never to occur, because the destruction of vtables occurs very close to shutdown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bee59-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bee59-105">Syntax</span></span>  
  
```  
HRESULT COMClassicVTableDestroyed(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bee59-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="bee59-106">Parameters</span></span>  
 `wrappedClasId`  
 <span data-ttu-id="bee59-107">[in] L'ID della classe per cui è stato creato l'oggetto vtable.</span><span class="sxs-lookup"><span data-stu-id="bee59-107">[in] The ID of the class for which this vtable was created.</span></span>  
  
 `implementedIID`  
 <span data-ttu-id="bee59-108">[in] L'ID dell'interfaccia implementata dalla classe.</span><span class="sxs-lookup"><span data-stu-id="bee59-108">[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="bee59-109">Questo valore può essere NULL se l'interfaccia è solo interno.</span><span class="sxs-lookup"><span data-stu-id="bee59-109">This value may be NULL if the interface is internal only.</span></span>  
  
 `pVTable`  
 <span data-ttu-id="bee59-110">[in] Un puntatore all'inizio dell'oggetto vtable.</span><span class="sxs-lookup"><span data-stu-id="bee59-110">[in] A pointer to the start of the vtable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bee59-111">Note</span><span class="sxs-lookup"><span data-stu-id="bee59-111">Remarks</span></span>  
 <span data-ttu-id="bee59-112">Il profiler non deve bloccare nella sua implementazione di questo metodo perché lo stack potrebbe non essere in uno stato che consente operazioni di garbage collection e pertanto non può essere attivata preemptive operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="bee59-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="bee59-113">Se il profiler qui si blocca e viene eseguito un tentativo di operazione di garbage collection, il runtime si bloccherà finché non restituisce questo callback.</span><span class="sxs-lookup"><span data-stu-id="bee59-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="bee59-114">Implementazione del profiler di questo metodo non è necessario chiamare codice gestito o causare in alcun modo un'allocazione di memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="bee59-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bee59-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bee59-115">Requirements</span></span>  
 <span data-ttu-id="bee59-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bee59-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bee59-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bee59-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bee59-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bee59-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bee59-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bee59-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bee59-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bee59-120">See Also</span></span>  
 [<span data-ttu-id="bee59-121">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="bee59-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="bee59-122">COMClassicVTableCreated (metodo)</span><span class="sxs-lookup"><span data-stu-id="bee59-122">COMClassicVTableCreated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtablecreated-method.md)

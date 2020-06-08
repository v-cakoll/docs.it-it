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
ms.openlocfilehash: 708981155589d491a3b1819adb611a28072dd1bf
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500319"
---
# <a name="icorprofilercallbackcomclassicvtabledestroyed-method"></a><span data-ttu-id="82728-102">Metodo ICorProfilerCallback::COMClassicVTableDestroyed</span><span class="sxs-lookup"><span data-stu-id="82728-102">ICorProfilerCallback::COMClassicVTableDestroyed Method</span></span>
<span data-ttu-id="82728-103">Notifica al profiler che un vtable di interoperabilità COM viene eliminato definitivamente.</span><span class="sxs-lookup"><span data-stu-id="82728-103">Notifies the profiler that a COM interop vtable is being destroyed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="82728-104">Questo callback probabilmente non si verificherà mai, perché la distruzione di vtable si verifica molto vicino alla chiusura.</span><span class="sxs-lookup"><span data-stu-id="82728-104">This callback is likely never to occur, because the destruction of vtables occurs very close to shutdown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82728-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="82728-105">Syntax</span></span>  
  
```cpp  
HRESULT COMClassicVTableDestroyed(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82728-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="82728-106">Parameters</span></span>

- `wrappedClassId`

  <span data-ttu-id="82728-107">\[in] ID della classe per la quale è stato creato questo vtable.</span><span class="sxs-lookup"><span data-stu-id="82728-107">\[in] The ID of the class for which this vtable was created.</span></span>

- `implementedIID`

  <span data-ttu-id="82728-108">\[in] ID dell'interfaccia implementata dalla classe.</span><span class="sxs-lookup"><span data-stu-id="82728-108">\[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="82728-109">Questo valore può essere NULL se l'interfaccia è solo interna.</span><span class="sxs-lookup"><span data-stu-id="82728-109">This value may be NULL if the interface is internal only.</span></span>

- `pVTable`

  <span data-ttu-id="82728-110">\[in] puntatore all'inizio di vtable.</span><span class="sxs-lookup"><span data-stu-id="82728-110">\[in] A pointer to the start of the vtable.</span></span>

## <a name="remarks"></a><span data-ttu-id="82728-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="82728-111">Remarks</span></span>  
 <span data-ttu-id="82728-112">Il profiler non deve bloccarsi nella sua implementazione di questo metodo perché lo stack potrebbe non trovarsi in uno stato che consente Garbage Collection e pertanto non è possibile abilitare il Garbage Collection preemptive.</span><span class="sxs-lookup"><span data-stu-id="82728-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="82728-113">Se il profiler si blocca qui e si tenta di Garbage Collection, il runtime si bloccherà fino a quando questo callback non viene restituito.</span><span class="sxs-lookup"><span data-stu-id="82728-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="82728-114">L'implementazione del profiler di questo metodo non deve chiamare nel codice gestito o in alcun modo causare un'allocazione della memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="82728-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82728-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="82728-115">Requirements</span></span>  
 <span data-ttu-id="82728-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82728-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82728-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="82728-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="82728-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82728-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82728-119">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82728-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82728-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82728-120">See also</span></span>

- [<span data-ttu-id="82728-121">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="82728-121">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="82728-122">Metodo COMClassicVTableCreated</span><span class="sxs-lookup"><span data-stu-id="82728-122">COMClassicVTableCreated Method</span></span>](icorprofilercallback-comclassicvtablecreated-method.md)

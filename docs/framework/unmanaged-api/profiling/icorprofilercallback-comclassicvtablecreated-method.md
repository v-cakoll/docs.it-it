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
ms.openlocfilehash: 79be2572f52ec509d9551261074204bf62ad5388
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445055"
---
# <a name="icorprofilercallbackcomclassicvtablecreated-method"></a><span data-ttu-id="b972b-102">Metodo ICorProfilerCallback::COMClassicVTableCreated</span><span class="sxs-lookup"><span data-stu-id="b972b-102">ICorProfilerCallback::COMClassicVTableCreated Method</span></span>
<span data-ttu-id="b972b-103">Notifica al profiler che è stato creato un vtable di interoperabilità COM per l'IID e la classe specificati.</span><span class="sxs-lookup"><span data-stu-id="b972b-103">Notifies the profiler that a COM interop vtable for the specified IID and class has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b972b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b972b-104">Syntax</span></span>  
  
```cpp  
HRESULT COMClassicVTableCreated(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable,  
    [in] ULONG   cSlots);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b972b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b972b-105">Parameters</span></span>  
 `wrappedClasId`  
 <span data-ttu-id="b972b-106">in ID della classe per cui è stato creato il vtable.</span><span class="sxs-lookup"><span data-stu-id="b972b-106">[in] The ID of the class for which the vtable has been created.</span></span>  
  
 `implementedIID`  
 <span data-ttu-id="b972b-107">in ID dell'interfaccia implementata dalla classe.</span><span class="sxs-lookup"><span data-stu-id="b972b-107">[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="b972b-108">Questo valore può essere NULL se l'interfaccia è solo interna.</span><span class="sxs-lookup"><span data-stu-id="b972b-108">This value may be NULL if the interface is internal only.</span></span>  
  
 `pVTable`  
 <span data-ttu-id="b972b-109">in Puntatore all'inizio di vtable.</span><span class="sxs-lookup"><span data-stu-id="b972b-109">[in] A pointer to the start of the vtable.</span></span>  
  
 `cSlots`  
 <span data-ttu-id="b972b-110">in Numero di slot presenti in vtable.</span><span class="sxs-lookup"><span data-stu-id="b972b-110">[in] The number of slots that are in the vtable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b972b-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b972b-111">Remarks</span></span>  
 <span data-ttu-id="b972b-112">Il profiler non deve bloccarsi nella sua implementazione di questo metodo perché lo stack potrebbe non trovarsi in uno stato che consente Garbage Collection e pertanto non è possibile abilitare il Garbage Collection preemptive.</span><span class="sxs-lookup"><span data-stu-id="b972b-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="b972b-113">Se il profiler si blocca qui e si tenta di Garbage Collection, il runtime si bloccherà fino a quando questo callback non viene restituito.</span><span class="sxs-lookup"><span data-stu-id="b972b-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="b972b-114">L'implementazione del profiler di questo metodo non deve chiamare nel codice gestito o in alcun modo causare un'allocazione della memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="b972b-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b972b-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b972b-115">Requirements</span></span>  
 <span data-ttu-id="b972b-116">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b972b-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b972b-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b972b-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b972b-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b972b-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b972b-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b972b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b972b-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b972b-120">See also</span></span>

- [<span data-ttu-id="b972b-121">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="b972b-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="b972b-122">Metodo COMClassicVTableDestroyed</span><span class="sxs-lookup"><span data-stu-id="b972b-122">COMClassicVTableDestroyed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtabledestroyed-method.md)

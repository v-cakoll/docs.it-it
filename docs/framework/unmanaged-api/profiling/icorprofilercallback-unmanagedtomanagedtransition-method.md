---
title: Metodo ICorProfilerCallback::UnmanagedToManagedTransition
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.UnmanagedToManagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition
helpviewer_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition method [.NET Framework profiling]
- UnmanagedToManagedTransition method [.NET Framework profiling]
ms.assetid: ade2cc01-9b81-4e09-a5f9-b3b9dda27e96
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 312f133c263becfd815f1b4ad48dff4892963aaf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041782"
---
# <a name="icorprofilercallbackunmanagedtomanagedtransition-method"></a><span data-ttu-id="4da5a-102">Metodo ICorProfilerCallback::UnmanagedToManagedTransition</span><span class="sxs-lookup"><span data-stu-id="4da5a-102">ICorProfilerCallback::UnmanagedToManagedTransition Method</span></span>
<span data-ttu-id="4da5a-103">Notifica al profiler che si è verificata una transizione da codice non gestito a codice gestito.</span><span class="sxs-lookup"><span data-stu-id="4da5a-103">Notifies the profiler that a transition from unmanaged code to managed code has occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4da5a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4da5a-104">Syntax</span></span>  
  
```  
HRESULT UnmanagedToManagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4da5a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4da5a-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="4da5a-106">[in] L'ID della funzione che viene chiamata.</span><span class="sxs-lookup"><span data-stu-id="4da5a-106">[in] The ID of the function that is being called.</span></span>  
  
 `reason`  
 <span data-ttu-id="4da5a-107">[in] Valore di [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumerazione che indica se si è verificata la transizione a causa di una chiamata al codice gestito dal codice non gestito o a causa la restituzione da una funzione non gestita chiamata da un equivalente gestito.</span><span class="sxs-lookup"><span data-stu-id="4da5a-107">[in] A value of the [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumeration that indicates whether the transition occurred because of a call into managed code from unmanaged code, or because of a return from an unmanaged function called by a managed one.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4da5a-108">Note</span><span class="sxs-lookup"><span data-stu-id="4da5a-108">Remarks</span></span>  
 <span data-ttu-id="4da5a-109">Se il valore di `reason` è COR_PRF_TRANSITION_RETURN e `functionId` è non null, la funzione ID è quello della funzione non gestita e non sarà mai stato compilato utilizzando il compilatore just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="4da5a-109">If the value of `reason` is COR_PRF_TRANSITION_RETURN and `functionId` is not null, the function ID is that of the unmanaged function, and will never have been compiled using the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="4da5a-110">Funzioni non gestite avere alcune informazioni di base associate, ad esempio un nome e alcuni metadati.</span><span class="sxs-lookup"><span data-stu-id="4da5a-110">Unmanaged functions have some basic information associated with them, such as a name and some metadata.</span></span>  
  
 <span data-ttu-id="4da5a-111">Se il valore di `reason` è COR_PRF_TRANSITION_CALL, è possibile che la funzione chiamata (vale a dire, la funzione gestita) non è ancora stato compilato tramite JIT.</span><span class="sxs-lookup"><span data-stu-id="4da5a-111">If the value of `reason` is COR_PRF_TRANSITION_CALL, it may be possible that the called function (that is, the managed function) has not yet been JIT-compiled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4da5a-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4da5a-112">Requirements</span></span>  
 <span data-ttu-id="4da5a-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4da5a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4da5a-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4da5a-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4da5a-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4da5a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4da5a-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4da5a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4da5a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4da5a-117">See also</span></span>

- [<span data-ttu-id="4da5a-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="4da5a-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="4da5a-119">Metodo ManagedToUnmanagedTransition</span><span class="sxs-lookup"><span data-stu-id="4da5a-119">ManagedToUnmanagedTransition Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)
- [<span data-ttu-id="4da5a-120">Uso esplicito di PInvoke in C++ (attributo DllImport)</span><span class="sxs-lookup"><span data-stu-id="4da5a-120">Using Explicit PInvoke in C++ (DllImport Attribute)</span></span>](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
- [<span data-ttu-id="4da5a-121">Uso delle funzionalità di interoperabilità C++ (PInvoke implicito)</span><span class="sxs-lookup"><span data-stu-id="4da5a-121">Using C++ Interop (Implicit PInvoke)</span></span>](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)

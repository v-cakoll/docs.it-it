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
ms.openlocfilehash: 8c4e132b90fa1f51bc6f858d75c159af212ec019
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439901"
---
# <a name="icorprofilercallbackunmanagedtomanagedtransition-method"></a><span data-ttu-id="f5ab3-102">Metodo ICorProfilerCallback::UnmanagedToManagedTransition</span><span class="sxs-lookup"><span data-stu-id="f5ab3-102">ICorProfilerCallback::UnmanagedToManagedTransition Method</span></span>
<span data-ttu-id="f5ab3-103">Notifica al profiler che è stata eseguita una transizione dal codice non gestito al codice gestito.</span><span class="sxs-lookup"><span data-stu-id="f5ab3-103">Notifies the profiler that a transition from unmanaged code to managed code has occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5ab3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f5ab3-104">Syntax</span></span>  
  
```cpp  
HRESULT UnmanagedToManagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5ab3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f5ab3-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="f5ab3-106">in ID della funzione chiamata.</span><span class="sxs-lookup"><span data-stu-id="f5ab3-106">[in] The ID of the function that is being called.</span></span>  
  
 `reason`  
 <span data-ttu-id="f5ab3-107">in Valore dell'enumerazione [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) che indica se si è verificata la transizione a causa di una chiamata al codice gestito da codice non gestito o a causa di un ritorno da una funzione non gestita chiamata da una funzione gestita.</span><span class="sxs-lookup"><span data-stu-id="f5ab3-107">[in] A value of the [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumeration that indicates whether the transition occurred because of a call into managed code from unmanaged code, or because of a return from an unmanaged function called by a managed one.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5ab3-108">Note</span><span class="sxs-lookup"><span data-stu-id="f5ab3-108">Remarks</span></span>  
 <span data-ttu-id="f5ab3-109">Se il valore di `reason` è COR_PRF_TRANSITION_RETURN e `functionId` non è null, l'ID funzione è quello della funzione non gestita e non sarà mai stato compilato con il compilatore JIT (just-in-Time).</span><span class="sxs-lookup"><span data-stu-id="f5ab3-109">If the value of `reason` is COR_PRF_TRANSITION_RETURN and `functionId` is not null, the function ID is that of the unmanaged function, and will never have been compiled using the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="f5ab3-110">Alle funzioni non gestite sono associate alcune informazioni di base, ad esempio un nome e alcuni metadati.</span><span class="sxs-lookup"><span data-stu-id="f5ab3-110">Unmanaged functions have some basic information associated with them, such as a name and some metadata.</span></span>  
  
 <span data-ttu-id="f5ab3-111">Se il valore di `reason` è COR_PRF_TRANSITION_CALL, potrebbe essere possibile che la funzione chiamata (ovvero la funzione gestita) non sia stata ancora compilata tramite JIT.</span><span class="sxs-lookup"><span data-stu-id="f5ab3-111">If the value of `reason` is COR_PRF_TRANSITION_CALL, it may be possible that the called function (that is, the managed function) has not yet been JIT-compiled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5ab3-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f5ab3-112">Requirements</span></span>  
 <span data-ttu-id="f5ab3-113">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5ab3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5ab3-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f5ab3-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f5ab3-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5ab3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5ab3-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5ab3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5ab3-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5ab3-117">See also</span></span>

- [<span data-ttu-id="f5ab3-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="f5ab3-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="f5ab3-119">Metodo ManagedToUnmanagedTransition</span><span class="sxs-lookup"><span data-stu-id="f5ab3-119">ManagedToUnmanagedTransition Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)
- [<span data-ttu-id="f5ab3-120">Uso esplicito di PInvoke in C++ (attributo DllImport)</span><span class="sxs-lookup"><span data-stu-id="f5ab3-120">Using Explicit PInvoke in C++ (DllImport Attribute)</span></span>](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
- [<span data-ttu-id="f5ab3-121">Uso delle funzionalità di interoperabilità C++ (PInvoke implicito)</span><span class="sxs-lookup"><span data-stu-id="f5ab3-121">Using C++ Interop (Implicit PInvoke)</span></span>](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)

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
ms.openlocfilehash: 8734fa9c9418b818cbe14ebe87ce2af6fa59c078
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499844"
---
# <a name="icorprofilercallbackunmanagedtomanagedtransition-method"></a><span data-ttu-id="2e6ab-102">Metodo ICorProfilerCallback::UnmanagedToManagedTransition</span><span class="sxs-lookup"><span data-stu-id="2e6ab-102">ICorProfilerCallback::UnmanagedToManagedTransition Method</span></span>
<span data-ttu-id="2e6ab-103">Notifica al profiler che è stata eseguita una transizione dal codice non gestito al codice gestito.</span><span class="sxs-lookup"><span data-stu-id="2e6ab-103">Notifies the profiler that a transition from unmanaged code to managed code has occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e6ab-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2e6ab-104">Syntax</span></span>  
  
```cpp  
HRESULT UnmanagedToManagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e6ab-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2e6ab-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="2e6ab-106">in ID della funzione chiamata.</span><span class="sxs-lookup"><span data-stu-id="2e6ab-106">[in] The ID of the function that is being called.</span></span>  
  
 `reason`  
 <span data-ttu-id="2e6ab-107">in Valore dell'enumerazione [COR_PRF_TRANSITION_REASON](cor-prf-transition-reason-enumeration.md) che indica se si è verificata la transizione a causa di una chiamata al codice gestito da codice non gestito o a causa di un ritorno da una funzione non gestita chiamata da una funzione gestita.</span><span class="sxs-lookup"><span data-stu-id="2e6ab-107">[in] A value of the [COR_PRF_TRANSITION_REASON](cor-prf-transition-reason-enumeration.md) enumeration that indicates whether the transition occurred because of a call into managed code from unmanaged code, or because of a return from an unmanaged function called by a managed one.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e6ab-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2e6ab-108">Remarks</span></span>  
 <span data-ttu-id="2e6ab-109">Se il valore di `reason` è COR_PRF_TRANSITION_RETURN e `functionId` non è null, l'ID funzione è quello della funzione non gestita e non sarà mai compilato con il compilatore JIT (just-in-Time).</span><span class="sxs-lookup"><span data-stu-id="2e6ab-109">If the value of `reason` is COR_PRF_TRANSITION_RETURN and `functionId` is not null, the function ID is that of the unmanaged function, and will never have been compiled using the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="2e6ab-110">Alle funzioni non gestite sono associate alcune informazioni di base, ad esempio un nome e alcuni metadati.</span><span class="sxs-lookup"><span data-stu-id="2e6ab-110">Unmanaged functions have some basic information associated with them, such as a name and some metadata.</span></span>  
  
 <span data-ttu-id="2e6ab-111">Se il valore di `reason` è COR_PRF_TRANSITION_CALL, potrebbe essere possibile che la funzione chiamata (ovvero la funzione gestita) non sia stata ancora compilata tramite JIT.</span><span class="sxs-lookup"><span data-stu-id="2e6ab-111">If the value of `reason` is COR_PRF_TRANSITION_CALL, it may be possible that the called function (that is, the managed function) has not yet been JIT-compiled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e6ab-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2e6ab-112">Requirements</span></span>  
 <span data-ttu-id="2e6ab-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e6ab-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e6ab-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2e6ab-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2e6ab-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e6ab-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e6ab-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e6ab-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e6ab-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e6ab-117">See also</span></span>

- [<span data-ttu-id="2e6ab-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="2e6ab-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="2e6ab-119">Metodo ManagedToUnmanagedTransition</span><span class="sxs-lookup"><span data-stu-id="2e6ab-119">ManagedToUnmanagedTransition Method</span></span>](icorprofilercallback-managedtounmanagedtransition-method.md)
- [<span data-ttu-id="2e6ab-120">Utilizzo di PInvoke esplicito in C++ (attributo DllImport)</span><span class="sxs-lookup"><span data-stu-id="2e6ab-120">Using Explicit PInvoke in C++ (DllImport Attribute)</span></span>](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
- [<span data-ttu-id="2e6ab-121">Uso dell'interoperabilità C++ (PInvoke implicito)</span><span class="sxs-lookup"><span data-stu-id="2e6ab-121">Using C++ Interop (Implicit PInvoke)</span></span>](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)

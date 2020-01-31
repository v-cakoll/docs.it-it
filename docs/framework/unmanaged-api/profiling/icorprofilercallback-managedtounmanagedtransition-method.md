---
title: Metodo ICorProfilerCallback::ManagedToUnmanagedTransition
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ManagedToUnmanagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ManagedToUnmanagedTransition
helpviewer_keywords:
- ManagedToUnmanagedTransition method [.NET Framework profiling]
- ICorProfilerCallback::ManagedToUnmanagedTransition method [.NET Framework profiling]
ms.assetid: ef3cd619-912d-40c5-a449-03ba02a39ee7
topic_type:
- apiref
ms.openlocfilehash: 0750ac66c654285e11dbbb5941f029bf5f900842
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866195"
---
# <a name="icorprofilercallbackmanagedtounmanagedtransition-method"></a><span data-ttu-id="e623c-102">Metodo ICorProfilerCallback::ManagedToUnmanagedTransition</span><span class="sxs-lookup"><span data-stu-id="e623c-102">ICorProfilerCallback::ManagedToUnmanagedTransition Method</span></span>
<span data-ttu-id="e623c-103">Notifica al profiler che è stata eseguita una transizione dal codice gestito al codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="e623c-103">Notifies the profiler that a transition from managed code to unmanaged code has occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e623c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e623c-104">Syntax</span></span>  
  
```cpp  
HRESULT ManagedToUnmanagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e623c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e623c-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="e623c-106">in ID della funzione chiamata.</span><span class="sxs-lookup"><span data-stu-id="e623c-106">[in] The ID of the function that is being called.</span></span>  
  
 `reason`  
 <span data-ttu-id="e623c-107">in Valore dell'enumerazione [COR_PRF_TRANSITION_REASON](cor-prf-transition-reason-enumeration.md) che indica se la transizione è stata eseguita a causa di una chiamata al codice non gestito dal codice gestito o a causa di un ritorno da una funzione gestita chiamata da una funzione non gestita.</span><span class="sxs-lookup"><span data-stu-id="e623c-107">[in] A value of the [COR_PRF_TRANSITION_REASON](cor-prf-transition-reason-enumeration.md) enumeration that indicates whether the transition occurred because of a call into unmanaged code from managed code, or because of a return from a managed function called by an unmanaged one.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e623c-108">Note</span><span class="sxs-lookup"><span data-stu-id="e623c-108">Remarks</span></span>  
 <span data-ttu-id="e623c-109">Se il valore di `reason` è COR_PRF_TRANSITION_CALL, l'ID funzione è quello della funzione non gestita, che non sarà mai stata compilata con il compilatore just-in-time.</span><span class="sxs-lookup"><span data-stu-id="e623c-109">If the value of `reason` is COR_PRF_TRANSITION_CALL, the function ID is that of the unmanaged function, which will never have been compiled using the just-in-time compiler.</span></span> <span data-ttu-id="e623c-110">Alle funzioni non gestite sono associate informazioni di base, ad esempio un nome e alcuni metadati.</span><span class="sxs-lookup"><span data-stu-id="e623c-110">Unmanaged functions have basic information associated with them, such as a name and some metadata.</span></span> <span data-ttu-id="e623c-111">Se la funzione non gestita è stata chiamata utilizzando Implicit platform invoke (PInvoke), il runtime non è in grado di determinare la destinazione della chiamata e il valore di `functionId` sarà null.</span><span class="sxs-lookup"><span data-stu-id="e623c-111">If the unmanaged function was called by using implicit platform invoke (PInvoke), the runtime cannot determine the destination of the call and the value of `functionId` will be null.</span></span> <span data-ttu-id="e623c-112">Per ulteriori informazioni su PInvoke implicito, [vedere C++ utilizzo dell'interoperabilità (PInvoke implicito)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).</span><span class="sxs-lookup"><span data-stu-id="e623c-112">For more information on implicit PInvoke, see [Using C++ Interop (Implicit PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e623c-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="e623c-113">Requirements</span></span>  
 <span data-ttu-id="e623c-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e623c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e623c-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e623c-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e623c-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e623c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e623c-117">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e623c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e623c-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e623c-118">See also</span></span>

- [<span data-ttu-id="e623c-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="e623c-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="e623c-120">Metodo UnmanagedToManagedTransition</span><span class="sxs-lookup"><span data-stu-id="e623c-120">UnmanagedToManagedTransition Method</span></span>](icorprofilercallback-unmanagedtomanagedtransition-method.md)
- [<span data-ttu-id="e623c-121">Uso esplicito di PInvoke in C++ (attributo DllImport)</span><span class="sxs-lookup"><span data-stu-id="e623c-121">Using Explicit PInvoke in C++ (DllImport Attribute)</span></span>](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)

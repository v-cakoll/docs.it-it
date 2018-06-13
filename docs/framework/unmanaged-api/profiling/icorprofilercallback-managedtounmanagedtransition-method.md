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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0735e4c59ba609ed87d61aca737c4f8a4dab757a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453486"
---
# <a name="icorprofilercallbackmanagedtounmanagedtransition-method"></a><span data-ttu-id="82eeb-102">Metodo ICorProfilerCallback::ManagedToUnmanagedTransition</span><span class="sxs-lookup"><span data-stu-id="82eeb-102">ICorProfilerCallback::ManagedToUnmanagedTransition Method</span></span>
<span data-ttu-id="82eeb-103">Notifica al profiler che si è verificata una transizione da codice gestito a codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="82eeb-103">Notifies the profiler that a transition from managed code to unmanaged code has occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82eeb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="82eeb-104">Syntax</span></span>  
  
```  
HRESULT ManagedToUnmanagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="82eeb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="82eeb-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="82eeb-106">[in] L'ID della funzione chiamata.</span><span class="sxs-lookup"><span data-stu-id="82eeb-106">[in] The ID of the function that is being called.</span></span>  
  
 `reason`  
 <span data-ttu-id="82eeb-107">[in] Il valore di [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumerazione che indica se la transizione si è verificato a causa di una chiamata nel codice non gestito da codice gestito o a causa di un ritorno da una funzione gestita chiamata da una non gestita.</span><span class="sxs-lookup"><span data-stu-id="82eeb-107">[in] A value of the [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumeration that indicates whether the transition occurred because of a call into unmanaged code from managed code, or because of a return from a managed function called by an unmanaged one.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82eeb-108">Note</span><span class="sxs-lookup"><span data-stu-id="82eeb-108">Remarks</span></span>  
 <span data-ttu-id="82eeb-109">Se il valore di `reason` è COR_PRF_TRANSITION_CALL, l'ID funzione che della funzione non gestita, che non verrà mai stata compilata utilizzando il compilatore just-in-time.</span><span class="sxs-lookup"><span data-stu-id="82eeb-109">If the value of `reason` is COR_PRF_TRANSITION_CALL, the function ID is that of the unmanaged function, which will never have been compiled using the just-in-time compiler.</span></span> <span data-ttu-id="82eeb-110">Funzioni non gestite sono le informazioni di base associate, ad esempio un nome e alcuni metadati.</span><span class="sxs-lookup"><span data-stu-id="82eeb-110">Unmanaged functions have basic information associated with them, such as a name and some metadata.</span></span> <span data-ttu-id="82eeb-111">Se la funzione non gestita è stata chiamata tramite implicita platform invoke (PInvoke), il runtime non è possibile determinare la destinazione della chiamata e il valore di `functionId` sarà null.</span><span class="sxs-lookup"><span data-stu-id="82eeb-111">If the unmanaged function was called by using implicit platform invoke (PInvoke), the runtime cannot determine the destination of the call and the value of `functionId` will be null.</span></span> <span data-ttu-id="82eeb-112">Per ulteriori informazioni su PInvoke implicito, vedere [utilizzando l'interoperabilità C++ (PInvoke implicito)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).</span><span class="sxs-lookup"><span data-stu-id="82eeb-112">For more information on implicit PInvoke, see [Using C++ Interop (Implicit PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82eeb-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="82eeb-113">Requirements</span></span>  
 <span data-ttu-id="82eeb-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82eeb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82eeb-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="82eeb-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="82eeb-116">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="82eeb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82eeb-117">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82eeb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82eeb-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82eeb-118">See Also</span></span>  
 [<span data-ttu-id="82eeb-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="82eeb-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="82eeb-120">Metodo UnmanagedToManagedTransition</span><span class="sxs-lookup"><span data-stu-id="82eeb-120">UnmanagedToManagedTransition Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)  
 [<span data-ttu-id="82eeb-121">Uso esplicito di PInvoke in C++ (attributo DllImport)</span><span class="sxs-lookup"><span data-stu-id="82eeb-121">Using Explicit PInvoke in C++ (DllImport Attribute)</span></span>](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)

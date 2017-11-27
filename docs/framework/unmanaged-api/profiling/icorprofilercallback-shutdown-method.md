---
title: Metodo ICorProfilerCallback::Shutdown
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.Shutdown
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::Shutdown
helpviewer_keywords:
- ICorProfilerCallback::Shutdown method [.NET Framework profiling]
- Shutdown method [.NET Framework profiling]
ms.assetid: 1ea194f0-a331-4855-a2ce-37393b8e5f84
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ea738414c21536377705260646e0f0684442492d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackshutdown-method"></a><span data-ttu-id="13c59-102">Metodo ICorProfilerCallback::Shutdown</span><span class="sxs-lookup"><span data-stu-id="13c59-102">ICorProfilerCallback::Shutdown Method</span></span>
<span data-ttu-id="13c59-103">Notifica al profiler che l'applicazione è in fase di chiusura.</span><span class="sxs-lookup"><span data-stu-id="13c59-103">Notifies the profiler that the application is shutting down.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13c59-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="13c59-104">Syntax</span></span>  
  
```  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a><span data-ttu-id="13c59-105">Note</span><span class="sxs-lookup"><span data-stu-id="13c59-105">Remarks</span></span>  
 <span data-ttu-id="13c59-106">Il codice del profiler non è possibile chiamare metodi del [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interfaccia dopo il `Shutdown` metodo viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="13c59-106">The profiler code cannot safely call methods of the [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interface after the `Shutdown` method is called.</span></span> <span data-ttu-id="13c59-107">Tutte le chiamate a `ICorProfilerInfo` metodi causare comportamenti imprevisti dopo il `Shutdown` metodo restituisce.</span><span class="sxs-lookup"><span data-stu-id="13c59-107">Any calls to `ICorProfilerInfo` methods result in undefined behavior after the `Shutdown` method returns.</span></span> <span data-ttu-id="13c59-108">Alcuni eventi non modificabili possono ancora verificarsi dopo l'arresto; il profiler deve fare attenzione a restituire immediatamente quando ciò si verifica.</span><span class="sxs-lookup"><span data-stu-id="13c59-108">Certain immutable events may still occur after shutdown; the profiler should take care to return immediately when this occurs.</span></span>  
  
 <span data-ttu-id="13c59-109">Il `Shutdown` metodo verrà chiamato solo se l'applicazione gestita che si sta profilando avviata come codice gestito (vale a dire iniziale gestito il frame dello stack di processo).</span><span class="sxs-lookup"><span data-stu-id="13c59-109">The `Shutdown` method will be called only if the managed application that is being profiled started as managed code (that is, the initial frame on the process stack is managed).</span></span> <span data-ttu-id="13c59-110">Se l'applicazione avviata come codice non gestito, ma in un secondo momento è passato in codice gestito, creando un'istanza di common language runtime (CLR), quindi `Shutdown` non verrà chiamato.</span><span class="sxs-lookup"><span data-stu-id="13c59-110">If the application started as unmanaged code but later jumped into managed code, thereby creating an instance of the common language runtime (CLR), then `Shutdown` will not be called.</span></span> <span data-ttu-id="13c59-111">In questi casi, il profiler deve essere inclusa nella libreria un `DllMain` valore routine che utilizzi il DLL_PROCESS_DETACH per liberare risorse ed eseguire l'elaborazione di pulizia dei dati, ad esempio svuotando le tracce su disco e così via.</span><span class="sxs-lookup"><span data-stu-id="13c59-111">For these cases, the profiler should include in its library a `DllMain` routine that uses the DLL_PROCESS_DETACH value to free any resources and perform clean-up processing of its data, such as flushing traces to disk and so on.</span></span>  
  
 <span data-ttu-id="13c59-112">In generale, il profiler deve far fronte ad arresti imprevisti.</span><span class="sxs-lookup"><span data-stu-id="13c59-112">In general, the profiler must cope with unexpected shutdowns.</span></span> <span data-ttu-id="13c59-113">Ad esempio, un processo venga arrestato dal Win32 `TerminateProcess` metodo (dichiarato in winbase).</span><span class="sxs-lookup"><span data-stu-id="13c59-113">For example, a process might be halted by Win32's `TerminateProcess` method (declared in Winbase.h).</span></span> <span data-ttu-id="13c59-114">In altri casi, Common Language Runtime arresterà alcuni thread gestiti (thread in background) senza il recapito dei messaggi di eliminazione per tali.</span><span class="sxs-lookup"><span data-stu-id="13c59-114">In other cases, the CLR will halt certain managed threads (background threads) without delivering orderly destruction messages for them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13c59-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="13c59-115">Requirements</span></span>  
 <span data-ttu-id="13c59-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13c59-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13c59-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="13c59-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="13c59-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13c59-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13c59-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13c59-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13c59-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13c59-120">See Also</span></span>  
 [<span data-ttu-id="13c59-121">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="13c59-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="13c59-122">Initialize (metodo)</span><span class="sxs-lookup"><span data-stu-id="13c59-122">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)

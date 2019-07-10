---
title: Enumerazione COR_PRF_SUSPEND_REASON
ms.date: 03/30/2017
api_name:
- COR_PRF_SUSPEND_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_SUSPEND_REASON
helpviewer_keywords:
- COR_PRF_SUSPEND_REASON enumeration [.NET Framework profiling]
ms.assetid: 75594833-bed3-47b2-a426-b75c5fe6fbcf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e084bc957eca9474078ed5ca3aef0276361dbe1b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745533"
---
# <a name="corprfsuspendreason-enumeration"></a><span data-ttu-id="b2752-102">Enumerazione COR_PRF_SUSPEND_REASON</span><span class="sxs-lookup"><span data-stu-id="b2752-102">COR_PRF_SUSPEND_REASON Enumeration</span></span>
<span data-ttu-id="b2752-103">Indica il motivo per cui il runtime è sospeso.</span><span class="sxs-lookup"><span data-stu-id="b2752-103">Indicates the reason that the runtime is suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2752-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b2752-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_SUSPEND_OTHER                   = 0x00,  
    COR_PRF_SUSPEND_FOR_GC                  = 0x01,  
    COR_PRF_SUSPEND_FOR_APPDOMAIN_SHUTDOWN  = 0x02,  
    COR_PRF_SUSPEND_FOR_CODE_PITCHING       = 0x03,  
    COR_PRF_SUSPEND_FOR_SHUTDOWN            = 0x04,  
    COR_PRF_SUSPEND_FOR_INPROC_DEBUGGER     = 0x06,  
    COR_PRF_SUSPEND_FOR_GC_PREP             = 0x07,    COR_PRF_SUSPEND_FOR_REJIT               = 8  
} COR_PRF_SUSPEND_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="b2752-105">Membri</span><span class="sxs-lookup"><span data-stu-id="b2752-105">Members</span></span>  
  
|<span data-ttu-id="b2752-106">Member</span><span class="sxs-lookup"><span data-stu-id="b2752-106">Member</span></span>|<span data-ttu-id="b2752-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b2752-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_SUSPEND_OTHER`|<span data-ttu-id="b2752-108">Il runtime viene sospeso per un motivo non specificato.</span><span class="sxs-lookup"><span data-stu-id="b2752-108">The runtime is suspended for an unspecified reason.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC`|<span data-ttu-id="b2752-109">Il runtime viene sospeso per la manutenzione di una richiesta di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="b2752-109">The runtime is suspended to service a garbage collection request.</span></span><br /><br /> <span data-ttu-id="b2752-110">I callback relative alla raccolta garbage verificano tra i [RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) e [RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) i callback.</span><span class="sxs-lookup"><span data-stu-id="b2752-110">The garbage collection-related callbacks occur between the [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) and [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_APPDOMAIN_SHUTDOWN`|<span data-ttu-id="b2752-111">La fase di esecuzione viene sospesa in modo che un `AppDomain` possono essere arrestate.</span><span class="sxs-lookup"><span data-stu-id="b2752-111">The runtime is suspended so that an `AppDomain` can be shut down.</span></span><br /><br /> <span data-ttu-id="b2752-112">Durante la fase di esecuzione viene sospesa, il runtime determina quali thread sono nel `AppDomain` vale a dire viene arrestato e impostarli in modo che abort durante la ripresa.</span><span class="sxs-lookup"><span data-stu-id="b2752-112">While the runtime is suspended, the runtime will determine which threads are in the `AppDomain` that is being shut down and set them to abort when they resume.</span></span> <span data-ttu-id="b2752-113">Esistono nessun `AppDomain`-callback specifico durante la sospensione.</span><span class="sxs-lookup"><span data-stu-id="b2752-113">There are no `AppDomain`-specific callbacks during this suspension.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_CODE_PITCHING`|<span data-ttu-id="b2752-114">La fase di esecuzione viene sospesa in modo che può verificarsi lancio del codice.</span><span class="sxs-lookup"><span data-stu-id="b2752-114">The runtime is suspended so that code pitching can occur.</span></span><br /><br /> <span data-ttu-id="b2752-115">Tale tecnica di codice viene utilizzata solo quando il compilatore JIT just-in-time è attivo con code pitching attivato.</span><span class="sxs-lookup"><span data-stu-id="b2752-115">Code pitching ensues only when the just-in-time (JIT) compiler is active with code pitching enabled.</span></span> <span data-ttu-id="b2752-116">Il codice callback pitching verificano tra i `ICorProfilerCallback::RuntimeSuspendFinished` e `ICorProfilerCallback::RuntimeResumeStarted` callback.</span><span class="sxs-lookup"><span data-stu-id="b2752-116">Code pitching callbacks occur between the `ICorProfilerCallback::RuntimeSuspendFinished` and `ICorProfilerCallback::RuntimeResumeStarted` callbacks.</span></span> <span data-ttu-id="b2752-117">**Nota:**  Il CLR JIT non lanciano funzioni in .NET Framework versione 2.0, in modo che questo valore non viene utilizzato in 2.0.</span><span class="sxs-lookup"><span data-stu-id="b2752-117">**Note:**  The CLR JIT does not pitch functions in the .NET Framework version 2.0, so this value is not used in 2.0.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_SHUTDOWN`|<span data-ttu-id="b2752-118">La fase di esecuzione viene sospesa in modo da poter essere arrestato.</span><span class="sxs-lookup"><span data-stu-id="b2752-118">The runtime is suspended so that it can shut down.</span></span> <span data-ttu-id="b2752-119">È necessario sospendere tutti i thread per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="b2752-119">It must suspend all threads to complete the operation.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_INPROC_DEBUGGER`|<span data-ttu-id="b2752-120">Il runtime viene sospeso per il debug in-process.</span><span class="sxs-lookup"><span data-stu-id="b2752-120">The runtime is suspended for in-process debugging.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC_PREP`|<span data-ttu-id="b2752-121">Il runtime viene sospeso per prepararsi per una garbage collection.</span><span class="sxs-lookup"><span data-stu-id="b2752-121">The runtime is suspended to prepare for a garbage collection.</span></span>|  
|`COR_PRF_SUSPEND_FOR_REJIT`|<span data-ttu-id="b2752-122">Il runtime viene sospeso per la ricompilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="b2752-122">The runtime is suspended for JIT recompilation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2752-123">Note</span><span class="sxs-lookup"><span data-stu-id="b2752-123">Remarks</span></span>  
 <span data-ttu-id="b2752-124">Sono consentiti tutti i thread di runtime in codice non gestito per continuare l'esecuzione fino a quando non tentano di immettere nuovamente la fase di esecuzione, a questo punto che verranno inoltre sospese fino a quando il runtime riprende.</span><span class="sxs-lookup"><span data-stu-id="b2752-124">All runtime threads that are in unmanaged code are permitted to continue running until they try to re-enter the runtime, at which point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="b2752-125">Questo vale anche per nuovi thread che accedono al runtime.</span><span class="sxs-lookup"><span data-stu-id="b2752-125">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="b2752-126">Tutti i thread all'interno del runtime vengono sospesi immediatamente se si trovano nel codice che possono essere interrotte o dover sospendere l'esecuzione al raggiungimento di codice che possono essere interrotte.</span><span class="sxs-lookup"><span data-stu-id="b2752-126">All threads within the runtime are either suspended immediately if they are in interruptible code, or asked to suspend when they do reach interruptible code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2752-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b2752-127">Requirements</span></span>  
 <span data-ttu-id="b2752-128">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2752-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2752-129">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b2752-129">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b2752-130">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2752-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2752-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2752-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2752-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2752-132">See also</span></span>

- [<span data-ttu-id="b2752-133">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="b2752-133">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)

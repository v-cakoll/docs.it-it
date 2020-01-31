---
title: Metodo ICorProfilerInfo2::GetNotifiedExceptionClauseInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetNotifiedExceptionClauseInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetNotifiedExceptionClauseInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetNotifiedExceptionCaluseInfo method [.NET Framework profiling]
- GetNotifiedExceptionCaluseInfo method [.NET Framework profiling]
ms.assetid: f9594a7e-cb0c-4c48-accb-29f762aa0c21
topic_type:
- apiref
ms.openlocfilehash: a430631948230d16e5d04c869625b4c670faaf02
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868642"
---
# <a name="icorprofilerinfo2getnotifiedexceptionclauseinfo-method"></a><span data-ttu-id="bd62c-102">Metodo ICorProfilerInfo2::GetNotifiedExceptionClauseInfo</span><span class="sxs-lookup"><span data-stu-id="bd62c-102">ICorProfilerInfo2::GetNotifiedExceptionClauseInfo Method</span></span>
<span data-ttu-id="bd62c-103">Ottiene l'indirizzo nativo e le informazioni sul frame per la clausola di eccezione (`catch`/`finally`/`filter`) che sta per essere eseguita o che è stata appena eseguita.</span><span class="sxs-lookup"><span data-stu-id="bd62c-103">Gets the native address and frame information for the exception clause (`catch`/`finally`/`filter`) that is about to be run or has just been run.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd62c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bd62c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNotifiedExceptionClauseInfo(  
    [out] COR_PRF_EX_CLAUSE_INFO *pinfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd62c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bd62c-105">Parameters</span></span>  
 `pinfo`  
 <span data-ttu-id="bd62c-106">out Puntatore a una struttura [COR_PRF_EX_CLAUSE_INFO](cor-prf-ex-clause-info-structure.md) che descrive l'istanza della clausola di eccezione corrente e il relativo frame associato.</span><span class="sxs-lookup"><span data-stu-id="bd62c-106">[out] A pointer to a [COR_PRF_EX_CLAUSE_INFO](cor-prf-ex-clause-info-structure.md) structure that describes the current exception clause instance and its associated frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd62c-107">Note</span><span class="sxs-lookup"><span data-stu-id="bd62c-107">Remarks</span></span>  
 <span data-ttu-id="bd62c-108">Quando viene ricevuta una notifica di eccezione, è possibile usare `GetNotifiedExceptionClauseInfo` per ottenere l'indirizzo nativo e le informazioni sul frame per la clausola Exception (`catch`/`finally`/`filter`) che sta per essere eseguito ([ICorProfilerCallback:: ExceptionCatcherEnter](icorprofilercallback-exceptioncatcherenter-method.md), [ICorProfilerCallback:: ExceptionUnwindFinallyEnter](icorprofilercallback-exceptionunwindfinallyenter-method.md)o [ICorProfilerCallback:: ExceptionSearchFilterEnter](icorprofilercallback-exceptionsearchfilterenter-method.md) callback ricevuto dal profiler) o è stato appena eseguito ([ICorProfilerCallback:: ExceptionCatcherLeave ](icorprofilercallback-exceptioncatcherleave-method.md), Il callback di [ICorProfilerCallback:: ExceptionUnwindFinallyLeave](icorprofilercallback-exceptionunwindfinallyleave-method.md)o [ICorProfilerCallback:: ExceptionSearchFilterLeave](icorprofilercallback-exceptionsearchfilterleave-method.md) è stato ricevuto dal profiler).</span><span class="sxs-lookup"><span data-stu-id="bd62c-108">When an exception notification is received, `GetNotifiedExceptionClauseInfo` can be used to get the native address and frame information for the exception clause (`catch`/`finally`/`filter`) that is about to be run ([ICorProfilerCallback::ExceptionCatcherEnter](icorprofilercallback-exceptioncatcherenter-method.md), [ICorProfilerCallback::ExceptionUnwindFinallyEnter](icorprofilercallback-exceptionunwindfinallyenter-method.md), or [ICorProfilerCallback::ExceptionSearchFilterEnter](icorprofilercallback-exceptionsearchfilterenter-method.md) callback is received by the profiler) or has just been run ([ICorProfilerCallback::ExceptionCatcherLeave](icorprofilercallback-exceptioncatcherleave-method.md), [ICorProfilerCallback::ExceptionUnwindFinallyLeave](icorprofilercallback-exceptionunwindfinallyleave-method.md), or [ICorProfilerCallback::ExceptionSearchFilterLeave](icorprofilercallback-exceptionsearchfilterleave-method.md) callback is received by the profiler).</span></span>  
  
 <span data-ttu-id="bd62c-109">Questa chiamata può essere eseguita in qualsiasi momento dopo uno dei callback di immissione precedenti fino a quando non viene ricevuto il callback di uscita corrispondente o viene generata un'eccezione annidata nella clausola corrente, nel qual caso non è presente alcuna notifica di uscita per tale clausola.</span><span class="sxs-lookup"><span data-stu-id="bd62c-109">This call can be made at any time after one of the Enter callbacks above until either the matching Leave callback is received or a nested exception is thrown in the current clause, in which case there is no Leave notification for that clause.</span></span> <span data-ttu-id="bd62c-110">Si noti che non è possibile che un'eccezione generata sfugga a un `filter` clausola Exception, quindi è sempre presente una notifica leave in questo caso.</span><span class="sxs-lookup"><span data-stu-id="bd62c-110">Note that it is not possible for a thrown exception to escape a `filter` exception clause, so there is always a Leave notification in that case.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd62c-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="bd62c-111">Requirements</span></span>  
 <span data-ttu-id="bd62c-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd62c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd62c-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bd62c-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bd62c-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd62c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd62c-115">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd62c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd62c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd62c-116">See also</span></span>

- [<span data-ttu-id="bd62c-117">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="bd62c-117">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="bd62c-118">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="bd62c-118">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)

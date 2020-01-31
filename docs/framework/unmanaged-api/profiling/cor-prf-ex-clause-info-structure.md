---
title: Struttura COR_PRF_EX_CLAUSE_INFO
ms.date: 03/30/2017
api_name:
- COR_PRF_EX_CLAUSE_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_EX_CLAUSE_INFO
helpviewer_keywords:
- COR_PRF_EX_CLAUSE_INFO structure [.NET Framework profiling]
ms.assetid: 7d0d6fb7-bc9d-40f0-8163-c0d162eaba7d
topic_type:
- apiref
ms.openlocfilehash: fb6d2e5fc21047fea0928137f983c553f9bb2bbd
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867282"
---
# <a name="cor_prf_ex_clause_info-structure"></a><span data-ttu-id="df5a2-102">Struttura COR_PRF_EX_CLAUSE_INFO</span><span class="sxs-lookup"><span data-stu-id="df5a2-102">COR_PRF_EX_CLAUSE_INFO Structure</span></span>
<span data-ttu-id="df5a2-103">Archivia le informazioni su un'istanza di una clausola di eccezione specifica e il relativo frame associato.</span><span class="sxs-lookup"><span data-stu-id="df5a2-103">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df5a2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="df5a2-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_PRF_EX_CLAUSE_INFO {  
    COR_PRF_CLAUSE_TYPE clauseType;  
    UINT_PTR programCounter;  
    UINT_PTR framePointer;  
    UINT_PTR shadowStackPointer;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="df5a2-105">Membri</span><span class="sxs-lookup"><span data-stu-id="df5a2-105">Members</span></span>  
  
|<span data-ttu-id="df5a2-106">Member</span><span class="sxs-lookup"><span data-stu-id="df5a2-106">Member</span></span>|<span data-ttu-id="df5a2-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="df5a2-107">Description</span></span>|  
|------------|-----------------|  
|`clauseType`|<span data-ttu-id="df5a2-108">Valore dell'enumerazione [COR_PRF_CLAUSE_TYPE](cor-prf-clause-type-enumeration.md) che specifica il tipo di clausola di eccezione che il codice è appena entrato o a sinistra.</span><span class="sxs-lookup"><span data-stu-id="df5a2-108">A value of the [COR_PRF_CLAUSE_TYPE](cor-prf-clause-type-enumeration.md) enumeration that specifies the type of exception clause the code just entered or left.</span></span>|  
|`programCounter`|<span data-ttu-id="df5a2-109">Il punto di ingresso nativo del gestore di clausole, ad esempio il contenuto del registro di un oggetto per il quale è stato x86.</span><span class="sxs-lookup"><span data-stu-id="df5a2-109">The native entry point of the clause handler — for example, the contents of the X86 EIP register.</span></span>|  
|`framePointer`|<span data-ttu-id="df5a2-110">Puntatore al frame logico per il gestore della clausola, ad esempio il contenuto del registro EBP x86.</span><span class="sxs-lookup"><span data-stu-id="df5a2-110">The pointer to the logical frame for the clause handler — for example, the contents of the X86 EBP register.</span></span>|  
|`shadowStackPointer`|<span data-ttu-id="df5a2-111">Puntatore allo stack di ombreggiatura.</span><span class="sxs-lookup"><span data-stu-id="df5a2-111">The pointer to the shadow stack.</span></span> <span data-ttu-id="df5a2-112">Questo valore è il contenuto del registro BSP e si applica solo a IA64.</span><span class="sxs-lookup"><span data-stu-id="df5a2-112">This value is the contents of the BSP register and applies only to IA64.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df5a2-113">Note</span><span class="sxs-lookup"><span data-stu-id="df5a2-113">Remarks</span></span>  
 <span data-ttu-id="df5a2-114">Quando viene ricevuta una notifica di eccezione, è possibile usare [ICorProfilerInfo2:: GetNotifiedExceptionClauseInfo](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) per ottenere le informazioni sull'indirizzo nativo e sul frame per la clausola exception (`catch`/`finally`/Filter) che sta per essere eseguita o che è stata appena eseguita.</span><span class="sxs-lookup"><span data-stu-id="df5a2-114">When an exception notification is received, [ICorProfilerInfo2::GetNotifiedExceptionClauseInfo](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) can be used to get the native address and frame information for the exception clause (`catch`/`finally`/filter) that is about to be run or has just been run.</span></span>  
  
 <span data-ttu-id="df5a2-115">L'esecuzione di una clausola di eccezione implica questi callback dal Common Language Runtime (CLR):</span><span class="sxs-lookup"><span data-stu-id="df5a2-115">Execution of an exception clause involves these callbacks from the common language runtime (CLR):</span></span>  
  
- [<span data-ttu-id="df5a2-116">ICorProfilerCallback::ExceptionCatcherEnter</span><span class="sxs-lookup"><span data-stu-id="df5a2-116">ICorProfilerCallback::ExceptionCatcherEnter</span></span>](icorprofilercallback-exceptioncatcherenter-method.md)  
  
- [<span data-ttu-id="df5a2-117">ICorProfilerCallback::ExceptionUnwindFinallyEnter</span><span class="sxs-lookup"><span data-stu-id="df5a2-117">ICorProfilerCallback::ExceptionUnwindFinallyEnter</span></span>](icorprofilercallback-exceptionunwindfinallyenter-method.md)  
  
- [<span data-ttu-id="df5a2-118">ICorProfilerCallback::ExceptionSearchFilterEnter</span><span class="sxs-lookup"><span data-stu-id="df5a2-118">ICorProfilerCallback::ExceptionSearchFilterEnter</span></span>](icorprofilercallback-exceptionsearchfilterenter-method.md)  
  
- [<span data-ttu-id="df5a2-119">ICorProfilerCallback::ExceptionCatcherLeave</span><span class="sxs-lookup"><span data-stu-id="df5a2-119">ICorProfilerCallback::ExceptionCatcherLeave</span></span>](icorprofilercallback-exceptioncatcherleave-method.md)  
  
- [<span data-ttu-id="df5a2-120">Metodo ICorProfilerCallback:: ExceptionUnwindFinallyLeave</span><span class="sxs-lookup"><span data-stu-id="df5a2-120">ICorProfilerCallback::ExceptionUnwindFinallyLeave</span></span>](icorprofilercallback-exceptionunwindfinallyleave-method.md)  
  
- [<span data-ttu-id="df5a2-121">Metodo ICorProfilerCallback:: ExceptionSearchFilterLeave</span><span class="sxs-lookup"><span data-stu-id="df5a2-121">ICorProfilerCallback::ExceptionSearchFilterLeave</span></span>](icorprofilercallback-exceptionsearchfilterleave-method.md)  
  
## <a name="requirements"></a><span data-ttu-id="df5a2-122">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="df5a2-122">Requirements</span></span>  
 <span data-ttu-id="df5a2-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df5a2-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df5a2-124">**Intestazione:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="df5a2-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="df5a2-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df5a2-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df5a2-126">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df5a2-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df5a2-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df5a2-127">See also</span></span>

- [<span data-ttu-id="df5a2-128">Strutture di profilatura</span><span class="sxs-lookup"><span data-stu-id="df5a2-128">Profiling Structures</span></span>](profiling-structures.md)

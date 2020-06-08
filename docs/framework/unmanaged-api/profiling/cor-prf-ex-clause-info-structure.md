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
ms.openlocfilehash: 5c764031f709eefe61022d0662f37bc5d3f3e281
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501001"
---
# <a name="cor_prf_ex_clause_info-structure"></a><span data-ttu-id="30be5-102">Struttura COR_PRF_EX_CLAUSE_INFO</span><span class="sxs-lookup"><span data-stu-id="30be5-102">COR_PRF_EX_CLAUSE_INFO Structure</span></span>
<span data-ttu-id="30be5-103">Archivia le informazioni su un'istanza di una clausola di eccezione specifica e il relativo frame associato.</span><span class="sxs-lookup"><span data-stu-id="30be5-103">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30be5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30be5-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_PRF_EX_CLAUSE_INFO {  
    COR_PRF_CLAUSE_TYPE clauseType;  
    UINT_PTR programCounter;  
    UINT_PTR framePointer;  
    UINT_PTR shadowStackPointer;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="30be5-105">Membri</span><span class="sxs-lookup"><span data-stu-id="30be5-105">Members</span></span>  
  
|<span data-ttu-id="30be5-106">Membro</span><span class="sxs-lookup"><span data-stu-id="30be5-106">Member</span></span>|<span data-ttu-id="30be5-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="30be5-107">Description</span></span>|  
|------------|-----------------|  
|`clauseType`|<span data-ttu-id="30be5-108">Valore dell'enumerazione [COR_PRF_CLAUSE_TYPE](cor-prf-clause-type-enumeration.md) che specifica il tipo di clausola di eccezione che il codice è appena entrato o a sinistra.</span><span class="sxs-lookup"><span data-stu-id="30be5-108">A value of the [COR_PRF_CLAUSE_TYPE](cor-prf-clause-type-enumeration.md) enumeration that specifies the type of exception clause the code just entered or left.</span></span>|  
|`programCounter`|<span data-ttu-id="30be5-109">Il punto di ingresso nativo del gestore di clausole, ad esempio il contenuto del registro di un oggetto per il quale è stato x86.</span><span class="sxs-lookup"><span data-stu-id="30be5-109">The native entry point of the clause handler — for example, the contents of the X86 EIP register.</span></span>|  
|`framePointer`|<span data-ttu-id="30be5-110">Puntatore al frame logico per il gestore della clausola, ad esempio il contenuto del registro EBP x86.</span><span class="sxs-lookup"><span data-stu-id="30be5-110">The pointer to the logical frame for the clause handler — for example, the contents of the X86 EBP register.</span></span>|  
|`shadowStackPointer`|<span data-ttu-id="30be5-111">Puntatore allo stack di ombreggiatura.</span><span class="sxs-lookup"><span data-stu-id="30be5-111">The pointer to the shadow stack.</span></span> <span data-ttu-id="30be5-112">Questo valore è il contenuto del registro BSP e si applica solo a IA64.</span><span class="sxs-lookup"><span data-stu-id="30be5-112">This value is the contents of the BSP register and applies only to IA64.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30be5-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="30be5-113">Remarks</span></span>  
 <span data-ttu-id="30be5-114">Quando viene ricevuta una notifica di eccezione, è possibile usare [ICorProfilerInfo2:: GetNotifiedExceptionClauseInfo](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) per ottenere l'indirizzo nativo e le informazioni sul frame per la clausola Exception ( `catch` / `finally` /Filter) che sta per essere eseguita o che è stata appena eseguita.</span><span class="sxs-lookup"><span data-stu-id="30be5-114">When an exception notification is received, [ICorProfilerInfo2::GetNotifiedExceptionClauseInfo](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) can be used to get the native address and frame information for the exception clause (`catch`/`finally`/filter) that is about to be run or has just been run.</span></span>  
  
 <span data-ttu-id="30be5-115">L'esecuzione di una clausola di eccezione implica questi callback dal Common Language Runtime (CLR):</span><span class="sxs-lookup"><span data-stu-id="30be5-115">Execution of an exception clause involves these callbacks from the common language runtime (CLR):</span></span>  
  
- [<span data-ttu-id="30be5-116">Metodo ICorProfilerCallback:: ExceptionCatcherEnter</span><span class="sxs-lookup"><span data-stu-id="30be5-116">ICorProfilerCallback::ExceptionCatcherEnter</span></span>](icorprofilercallback-exceptioncatcherenter-method.md)  
  
- [<span data-ttu-id="30be5-117">Metodo ICorProfilerCallback:: ExceptionUnwindFinallyEnter</span><span class="sxs-lookup"><span data-stu-id="30be5-117">ICorProfilerCallback::ExceptionUnwindFinallyEnter</span></span>](icorprofilercallback-exceptionunwindfinallyenter-method.md)  
  
- [<span data-ttu-id="30be5-118">Metodo ICorProfilerCallback:: ExceptionSearchFilterEnter</span><span class="sxs-lookup"><span data-stu-id="30be5-118">ICorProfilerCallback::ExceptionSearchFilterEnter</span></span>](icorprofilercallback-exceptionsearchfilterenter-method.md)  
  
- [<span data-ttu-id="30be5-119">Metodo ICorProfilerCallback:: ExceptionCatcherLeave</span><span class="sxs-lookup"><span data-stu-id="30be5-119">ICorProfilerCallback::ExceptionCatcherLeave</span></span>](icorprofilercallback-exceptioncatcherleave-method.md)  
  
- [<span data-ttu-id="30be5-120">Metodo ICorProfilerCallback:: ExceptionUnwindFinallyLeave</span><span class="sxs-lookup"><span data-stu-id="30be5-120">ICorProfilerCallback::ExceptionUnwindFinallyLeave</span></span>](icorprofilercallback-exceptionunwindfinallyleave-method.md)  
  
- [<span data-ttu-id="30be5-121">Metodo ICorProfilerCallback:: ExceptionSearchFilterLeave</span><span class="sxs-lookup"><span data-stu-id="30be5-121">ICorProfilerCallback::ExceptionSearchFilterLeave</span></span>](icorprofilercallback-exceptionsearchfilterleave-method.md)  
  
## <a name="requirements"></a><span data-ttu-id="30be5-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="30be5-122">Requirements</span></span>  
 <span data-ttu-id="30be5-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30be5-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30be5-124">**Intestazione:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="30be5-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="30be5-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30be5-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30be5-126">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30be5-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30be5-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30be5-127">See also</span></span>

- [<span data-ttu-id="30be5-128">Strutture di profilatura</span><span class="sxs-lookup"><span data-stu-id="30be5-128">Profiling Structures</span></span>](profiling-structures.md)

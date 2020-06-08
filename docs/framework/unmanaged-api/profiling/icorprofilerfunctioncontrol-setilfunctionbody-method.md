---
title: Metodo ICorProfilerFunctionControl::SetILFunctionBody
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 2c33f0f7-75b2-4c19-b2c7-c94b54997576
topic_type:
- apiref
ms.openlocfilehash: a6b24fd59a183a4a59b117663772417d55cc67db
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503140"
---
# <a name="icorprofilerfunctioncontrolsetilfunctionbody-method"></a><span data-ttu-id="bdf92-102">Metodo ICorProfilerFunctionControl::SetILFunctionBody</span><span class="sxs-lookup"><span data-stu-id="bdf92-102">ICorProfilerFunctionControl::SetILFunctionBody Method</span></span>
<span data-ttu-id="bdf92-103">Sostituisce il corpo Common Intermediate Language (CIL) del metodo.</span><span class="sxs-lookup"><span data-stu-id="bdf92-103">Replaces the Common Intermediate Language (CIL) body of the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdf92-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bdf92-104">Syntax</span></span>  
  
```cpp  
HRESULT SetILFunctionBody(  
    [in]  ULONG   cbNewILMethodHeader,  
    [in, size_is(cbNewILMethodHeader)] LPCBYTE pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bdf92-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bdf92-105">Parameters</span></span>  
 `cbNewILMethodHeader`  
 <span data-ttu-id="bdf92-106">[in] Dimensioni totali del nuovo codice CIL, incluse l'intestazione e tutte strutture successive al corpo.</span><span class="sxs-lookup"><span data-stu-id="bdf92-106">[in] The total size of the new CIL, including the header and any structures that come after the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="bdf92-107">[in] Puntatore alla nuova intestazione CIL.</span><span class="sxs-lookup"><span data-stu-id="bdf92-107">[in] A pointer to the new CIL header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bdf92-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bdf92-108">Return Value</span></span>  
 <span data-ttu-id="bdf92-109">Questo metodo restituisce gli HRESULT specifici seguenti.</span><span class="sxs-lookup"><span data-stu-id="bdf92-109">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="bdf92-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bdf92-110">HRESULT</span></span>|<span data-ttu-id="bdf92-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bdf92-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bdf92-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="bdf92-112">S_OK</span></span>|<span data-ttu-id="bdf92-113">Sostituzione completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="bdf92-113">The replacement was successful.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bdf92-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="bdf92-114">Remarks</span></span>  
 <span data-ttu-id="bdf92-115">A differenza del metodo [ICorProfilerInfo:: SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) , il `SetILFunctionBody` metodo gestisce la memoria necessaria per il nuovo corpo CIL.</span><span class="sxs-lookup"><span data-stu-id="bdf92-115">Unlike the [ICorProfilerInfo::SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) method, the `SetILFunctionBody` method manages the memory required for the new CIL body.</span></span> <span data-ttu-id="bdf92-116">Ciò significa che il corpo del CIL fornito dal profiler non deve essere allocato tramite l'interfaccia [IMethodMalloc](imethodmalloc-interface.md) o allocato in un intervallo specifico.</span><span class="sxs-lookup"><span data-stu-id="bdf92-116">This means that the CIL body provided by the profiler does not have to be allocated by using the [IMethodMalloc](imethodmalloc-interface.md) interface or allocated within a particular range.</span></span> <span data-ttu-id="bdf92-117">ma può essere allocato in qualsiasi heap.</span><span class="sxs-lookup"><span data-stu-id="bdf92-117">It can be allocated on any heap.</span></span> <span data-ttu-id="bdf92-118">Il profiler può liberare la memoria usata per il corpo CIL dopo la `SetILFunctionBody` restituzione.</span><span class="sxs-lookup"><span data-stu-id="bdf92-118">The profiler can free the memory used for its CIL body after `SetILFunctionBody` returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdf92-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bdf92-119">Requirements</span></span>  
 <span data-ttu-id="bdf92-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bdf92-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdf92-121">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bdf92-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bdf92-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bdf92-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bdf92-123">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdf92-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdf92-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bdf92-124">See also</span></span>

- [<span data-ttu-id="bdf92-125">Interfaccia ICorProfilerFunctionControl</span><span class="sxs-lookup"><span data-stu-id="bdf92-125">ICorProfilerFunctionControl Interface</span></span>](icorprofilerfunctioncontrol-interface.md)

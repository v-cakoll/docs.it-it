---
title: Metodo ICorProfilerInfo4::EnumThreads
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.EnumThreads
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::EnumThreads
helpviewer_keywords:
- ICorProfilerInfo4::EnumThreads method [.NET Framework profiling]
- EnumThreads method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: bca7a5b4-c207-4894-918c-0733926296dd
topic_type:
- apiref
ms.openlocfilehash: d42c86a458661d3559f99235a6d5b208c82d1963
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502808"
---
# <a name="icorprofilerinfo4enumthreads-method"></a><span data-ttu-id="9de31-102">Metodo ICorProfilerInfo4::EnumThreads</span><span class="sxs-lookup"><span data-stu-id="9de31-102">ICorProfilerInfo4::EnumThreads Method</span></span>
<span data-ttu-id="9de31-103">Restituisce un enumeratore che fornisce i metodi per scorrere in sequenza l'insieme di tutti i thread gestiti nel processo profilato.</span><span class="sxs-lookup"><span data-stu-id="9de31-103">Returns an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9de31-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9de31-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9de31-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9de31-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="9de31-106">out Puntatore a un'interfaccia [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="9de31-106">[out] A pointer to an [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9de31-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9de31-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9de31-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9de31-108">Requirements</span></span>  
 <span data-ttu-id="9de31-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9de31-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9de31-110">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9de31-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9de31-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9de31-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9de31-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9de31-112">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9de31-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9de31-113">See also</span></span>

- [<span data-ttu-id="9de31-114">Interfaccia ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="9de31-114">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="9de31-115">Interfaccia ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="9de31-115">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="9de31-116">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="9de31-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="9de31-117">Profilatura</span><span class="sxs-lookup"><span data-stu-id="9de31-117">Profiling</span></span>](index.md)

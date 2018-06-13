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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6c394690f6c8d7f3618b385b0a1432fc396fb819
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458020"
---
# <a name="icorprofilerinfo4enumthreads-method"></a><span data-ttu-id="facbe-102">Metodo ICorProfilerInfo4::EnumThreads</span><span class="sxs-lookup"><span data-stu-id="facbe-102">ICorProfilerInfo4::EnumThreads Method</span></span>
<span data-ttu-id="facbe-103">Restituisce un enumeratore che fornisce i metodi per scorrere in sequenza la raccolta di tutti i thread gestiti nel processo profilato.</span><span class="sxs-lookup"><span data-stu-id="facbe-103">Returns an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="facbe-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="facbe-104">Syntax</span></span>  
  
```  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="facbe-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="facbe-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="facbe-106">[out] Un puntatore a un [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="facbe-106">[out] A pointer to an [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="facbe-107">Note</span><span class="sxs-lookup"><span data-stu-id="facbe-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="facbe-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="facbe-108">Requirements</span></span>  
 <span data-ttu-id="facbe-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="facbe-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="facbe-110">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="facbe-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="facbe-111">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="facbe-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="facbe-112">**Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="facbe-112">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="facbe-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="facbe-113">See Also</span></span>  
 [<span data-ttu-id="facbe-114">Interfaccia ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="facbe-114">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 [<span data-ttu-id="facbe-115">Interfaccia ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="facbe-115">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [<span data-ttu-id="facbe-116">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="facbe-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="facbe-117">Profilatura</span><span class="sxs-lookup"><span data-stu-id="facbe-117">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)

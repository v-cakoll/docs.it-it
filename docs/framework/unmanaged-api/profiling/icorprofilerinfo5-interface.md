---
title: Interfaccia ICorProfilerInfo5
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo5
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 7bd48c34-37ed-4230-9eec-39a17280f05d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b249605833e8fbd219495ab92bebc2eff6177eb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049440"
---
# <a name="icorprofilerinfo5-interface"></a><span data-ttu-id="2f0f3-102">Interfaccia ICorProfilerInfo5</span><span class="sxs-lookup"><span data-stu-id="2f0f3-102">ICorProfilerInfo5 Interface</span></span>
<span data-ttu-id="2f0f3-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="2f0f3-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="2f0f3-104">Una sottoclasse [ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md) che fornisce metodi usati dal code profiler di comunicare con common language runtime (CLR) per controllare il monitoraggio degli eventi.</span><span class="sxs-lookup"><span data-stu-id="2f0f3-104">A subclass of [ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md) that provides methods for use by code profilers to communicate with the common language runtime (CLR) to control event monitoring.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2f0f3-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="2f0f3-105">Methods</span></span>  
  
|<span data-ttu-id="2f0f3-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="2f0f3-106">Method</span></span>|<span data-ttu-id="2f0f3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2f0f3-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2f0f3-108">Metodo GetEventMask2</span><span class="sxs-lookup"><span data-stu-id="2f0f3-108">GetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)|<span data-ttu-id="2f0f3-109">Ottiene le categorie di eventi correnti per le quali il profiler richiede la ricezione delle notifiche da CLR.</span><span class="sxs-lookup"><span data-stu-id="2f0f3-109">Gets the current event categories for which the profiler wants to receive notifications from the CLR.</span></span>|  
|[<span data-ttu-id="2f0f3-110">Metodo SetEventMask2</span><span class="sxs-lookup"><span data-stu-id="2f0f3-110">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)|<span data-ttu-id="2f0f3-111">Imposta un valore che specifica i tipi di eventi per i quali il profiler richiede la ricezione della notifica da CLR.</span><span class="sxs-lookup"><span data-stu-id="2f0f3-111">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f0f3-112">Note</span><span class="sxs-lookup"><span data-stu-id="2f0f3-112">Remarks</span></span>  
 <span data-ttu-id="2f0f3-113">I metodi disponibili in questa interfaccia sono progettati per sostituire il [ICorProfilerInfo:: GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) e [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) metodi.</span><span class="sxs-lookup"><span data-stu-id="2f0f3-113">The methods available on this interface are intended to replace the [ICorProfilerInfo::GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) and [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f0f3-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2f0f3-114">Requirements</span></span>  
 <span data-ttu-id="2f0f3-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f0f3-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f0f3-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2f0f3-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2f0f3-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f0f3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f0f3-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f0f3-118">See also</span></span>

- [<span data-ttu-id="2f0f3-119">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="2f0f3-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)

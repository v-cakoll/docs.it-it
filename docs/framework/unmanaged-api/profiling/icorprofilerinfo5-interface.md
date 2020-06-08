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
ms.openlocfilehash: 82f6262c2c576b49be4e7fcaa14043950df4c67a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495627"
---
# <a name="icorprofilerinfo5-interface"></a><span data-ttu-id="de481-102">Interfaccia ICorProfilerInfo5</span><span class="sxs-lookup"><span data-stu-id="de481-102">ICorProfilerInfo5 Interface</span></span>
<span data-ttu-id="de481-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="de481-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="de481-104">Sottoclasse di [ICorProfilerInfo4](icorprofilerinfo4-interface.md) che fornisce i metodi per l'uso da parte dei profiler del codice per comunicare con il Common Language Runtime (CLR) per controllare il monitoraggio degli eventi.</span><span class="sxs-lookup"><span data-stu-id="de481-104">A subclass of [ICorProfilerInfo4](icorprofilerinfo4-interface.md) that provides methods for use by code profilers to communicate with the common language runtime (CLR) to control event monitoring.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="de481-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="de481-105">Methods</span></span>  
  
|<span data-ttu-id="de481-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="de481-106">Method</span></span>|<span data-ttu-id="de481-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="de481-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="de481-108">Metodo GetEventMask2</span><span class="sxs-lookup"><span data-stu-id="de481-108">GetEventMask2 Method</span></span>](icorprofilerinfo5-geteventmask2-method.md)|<span data-ttu-id="de481-109">Ottiene le categorie di eventi correnti per le quali il profiler richiede la ricezione delle notifiche da CLR.</span><span class="sxs-lookup"><span data-stu-id="de481-109">Gets the current event categories for which the profiler wants to receive notifications from the CLR.</span></span>|  
|[<span data-ttu-id="de481-110">Metodo SetEventMask2</span><span class="sxs-lookup"><span data-stu-id="de481-110">SetEventMask2 Method</span></span>](icorprofilerinfo5-seteventmask2-method.md)|<span data-ttu-id="de481-111">Imposta un valore che specifica i tipi di eventi per i quali il profiler richiede la ricezione della notifica da CLR.</span><span class="sxs-lookup"><span data-stu-id="de481-111">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de481-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="de481-112">Remarks</span></span>  
 <span data-ttu-id="de481-113">I metodi disponibili in questa interfaccia hanno lo scopo di sostituire i metodi [ICorProfilerInfo:: GetEventMask](icorprofilerinfo-geteventmask-method.md) e [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) .</span><span class="sxs-lookup"><span data-stu-id="de481-113">The methods available on this interface are intended to replace the [ICorProfilerInfo::GetEventMask](icorprofilerinfo-geteventmask-method.md) and [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de481-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="de481-114">Requirements</span></span>  
 <span data-ttu-id="de481-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de481-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de481-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="de481-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="de481-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de481-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de481-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de481-118">See also</span></span>

- [<span data-ttu-id="de481-119">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="de481-119">Profiling Interfaces</span></span>](profiling-interfaces.md)

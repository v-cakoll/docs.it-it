---
title: Metodo ICorProfilerCallback::ObjectsAllocatedByClass
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectsAllocatedByClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectsAllocatedByClass
helpviewer_keywords:
- ObjectsAllocatedByClass method [.NET Framework profiling]
- ICorProfilerCallback::ObjectsAllocatedByClass method [.NET Framework profiling]
ms.assetid: 91d688f3-a80e-419d-9755-ff94bc04188a
topic_type:
- apiref
ms.openlocfilehash: 028207486f43e35086ed2e515eb3ae6bca304491
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866076"
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a><span data-ttu-id="25925-102">Metodo ICorProfilerCallback::ObjectsAllocatedByClass</span><span class="sxs-lookup"><span data-stu-id="25925-102">ICorProfilerCallback::ObjectsAllocatedByClass Method</span></span>
<span data-ttu-id="25925-103">Notifica al profiler il numero di istanze di ogni classe specificata create dopo la Garbage Collection più recente.</span><span class="sxs-lookup"><span data-stu-id="25925-103">Notifies the profiler about the number of instances of each specified class that have been created since the most recent garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25925-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="25925-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="25925-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="25925-105">Parameters</span></span>  
 `cClassCount`  
 <span data-ttu-id="25925-106">in Dimensioni delle matrici `classIds` e `cObjects`.</span><span class="sxs-lookup"><span data-stu-id="25925-106">[in] The size of the `classIds` and `cObjects` arrays.</span></span>  
  
 `classIds`  
 <span data-ttu-id="25925-107">in Matrice di ID di classe, in cui ogni ID specifica una classe con una o più istanze.</span><span class="sxs-lookup"><span data-stu-id="25925-107">[in] An array of class IDs, where each ID specifies a class with one or more instances.</span></span>  
  
 `cObjects`  
 <span data-ttu-id="25925-108">in Matrice di numeri interi, dove ogni numero intero specifica il numero di istanze per la classe corrispondente nella matrice `classIds`.</span><span class="sxs-lookup"><span data-stu-id="25925-108">[in] An array of integers, where each integer specifies the number of instances for the corresponding class in the `classIds` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25925-109">Note</span><span class="sxs-lookup"><span data-stu-id="25925-109">Remarks</span></span>  
 <span data-ttu-id="25925-110">Le matrici `classIds` e `cObjects` sono matrici parallele.</span><span class="sxs-lookup"><span data-stu-id="25925-110">The `classIds` and `cObjects` arrays are parallel arrays.</span></span> <span data-ttu-id="25925-111">Ad esempio, `classIds[i]` e `cObjects[i]` fanno riferimento alla stessa classe.</span><span class="sxs-lookup"><span data-stu-id="25925-111">For example, `classIds[i]` and `cObjects[i]` reference the same class.</span></span> <span data-ttu-id="25925-112">Se non è stata creata alcuna istanza di una classe dalla Garbage Collection precedente, la classe viene omessa.</span><span class="sxs-lookup"><span data-stu-id="25925-112">If no instance of a class has been created since the previous garbage collection, the class is omitted.</span></span> <span data-ttu-id="25925-113">Il callback `ObjectsAllocatedByClass` non segnalerà gli oggetti allocati nell'heap degli oggetti grandi.</span><span class="sxs-lookup"><span data-stu-id="25925-113">The `ObjectsAllocatedByClass` callback will not report objects allocated in the large object heap.</span></span>  
  
 <span data-ttu-id="25925-114">I numeri segnalati da `ObjectsAllocatedByClass` sono solo stime.</span><span class="sxs-lookup"><span data-stu-id="25925-114">The numbers reported by `ObjectsAllocatedByClass` are only estimates.</span></span> <span data-ttu-id="25925-115">Per i conteggi esatti, utilizzare [ICorProfilerCallback:: ObjectAllocated](icorprofilercallback-objectallocated-method.md).</span><span class="sxs-lookup"><span data-stu-id="25925-115">For exact counts, use [ICorProfilerCallback::ObjectAllocated](icorprofilercallback-objectallocated-method.md).</span></span>  
  
 <span data-ttu-id="25925-116">La matrice di `classIds` può contenere una o più voci null se la matrice `cObjects` corrispondente contiene tipi che stanno scaricando.</span><span class="sxs-lookup"><span data-stu-id="25925-116">The `classIds` array may contain one or more null entries if the corresponding `cObjects` array has types that are unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25925-117">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="25925-117">Requirements</span></span>  
 <span data-ttu-id="25925-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25925-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25925-119">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="25925-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="25925-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25925-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25925-121">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25925-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25925-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25925-122">See also</span></span>

- [<span data-ttu-id="25925-123">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="25925-123">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)

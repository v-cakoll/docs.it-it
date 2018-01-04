---
title: Metodo ICorProfilerInfo2::GetBoxClassLayout
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetBoxClassLayout
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetBoxClassLayout
helpviewer_keywords:
- GetBoxClassLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetBoxClassLayout method [.NET Framework profiling]
ms.assetid: 624672b5-1189-488a-85d2-3e12b49617c1
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9ef6df997a4ba4369b87789e47ac7ead2206162e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a><span data-ttu-id="5d0f8-102">Metodo ICorProfilerInfo2::GetBoxClassLayout</span><span class="sxs-lookup"><span data-stu-id="5d0f8-102">ICorProfilerInfo2::GetBoxClassLayout Method</span></span>
<span data-ttu-id="5d0f8-103">Ottiene informazioni sul tipo di valore specificato in cui si trova quando viene sottoposto a boxing.</span><span class="sxs-lookup"><span data-stu-id="5d0f8-103">Gets information about where the specified value type is located when it is boxed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d0f8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5d0f8-104">Syntax</span></span>  
  
```  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5d0f8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5d0f8-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="5d0f8-106">[in] L'ID della classe che descrive il tipo di valore boxed.</span><span class="sxs-lookup"><span data-stu-id="5d0f8-106">[in] The ID of the class that describes the value type that is boxed.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="5d0f8-107">[out] Valore intero che rappresenta l'offset, rispetto al puntatore all'ID dell'oggetto di tipo boxed, del tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="5d0f8-107">[out] An integer that is the offset, relative to the boxed object ID pointer, of the value type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d0f8-108">Note</span><span class="sxs-lookup"><span data-stu-id="5d0f8-108">Remarks</span></span>  
 <span data-ttu-id="5d0f8-109">Il `pBufferOffset` valore rappresenta il percorso del tipo di valore all'interno di una casella.</span><span class="sxs-lookup"><span data-stu-id="5d0f8-109">The `pBufferOffset` value is the location of the value type within a box.</span></span> <span data-ttu-id="5d0f8-110">Dopo aver `pBufferOffset` viene applicato a un oggetto boxed, layout della classe del tipo di valore può essere utilizzato per interpretare il valore dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="5d0f8-110">After `pBufferOffset` is applied to a boxed object, the value type's class layout can be used to interpret the object's value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d0f8-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5d0f8-111">Requirements</span></span>  
 <span data-ttu-id="5d0f8-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d0f8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d0f8-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5d0f8-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5d0f8-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d0f8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d0f8-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d0f8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d0f8-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d0f8-116">See Also</span></span>  
 [<span data-ttu-id="5d0f8-117">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="5d0f8-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="5d0f8-118">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="5d0f8-118">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)

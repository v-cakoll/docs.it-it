---
title: Metodo ICorProfilerInfo2::GetBoxClassLayout
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetBoxClassLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetBoxClassLayout
helpviewer_keywords:
- GetBoxClassLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetBoxClassLayout method [.NET Framework profiling]
ms.assetid: 624672b5-1189-488a-85d2-3e12b49617c1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4dac7e38d1e767a3edeef932a0c0916daffe24b8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092032"
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a><span data-ttu-id="837d3-102">Metodo ICorProfilerInfo2::GetBoxClassLayout</span><span class="sxs-lookup"><span data-stu-id="837d3-102">ICorProfilerInfo2::GetBoxClassLayout Method</span></span>
<span data-ttu-id="837d3-103">Ottiene informazioni su dove si trova il tipo di valore specificato quando è sottoposto a boxing.</span><span class="sxs-lookup"><span data-stu-id="837d3-103">Gets information about where the specified value type is located when it is boxed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="837d3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="837d3-104">Syntax</span></span>  
  
```  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="837d3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="837d3-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="837d3-106">[in] L'ID della classe che descrive il tipo di valore boxed.</span><span class="sxs-lookup"><span data-stu-id="837d3-106">[in] The ID of the class that describes the value type that is boxed.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="837d3-107">[out] Valore intero che rappresenta l'offset, relativo al puntatore, ID di oggetto boxed del tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="837d3-107">[out] An integer that is the offset, relative to the boxed object ID pointer, of the value type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="837d3-108">Note</span><span class="sxs-lookup"><span data-stu-id="837d3-108">Remarks</span></span>  
 <span data-ttu-id="837d3-109">Il `pBufferOffset` valore rappresenta il percorso del tipo di valore all'interno di una finestra.</span><span class="sxs-lookup"><span data-stu-id="837d3-109">The `pBufferOffset` value is the location of the value type within a box.</span></span> <span data-ttu-id="837d3-110">Dopo aver `pBufferOffset` viene applicato a un oggetto sottoposto a conversione boxing, layout di classe del tipo di valore può essere utilizzato per interpretare il valore dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="837d3-110">After `pBufferOffset` is applied to a boxed object, the value type's class layout can be used to interpret the object's value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="837d3-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="837d3-111">Requirements</span></span>  
 <span data-ttu-id="837d3-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="837d3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="837d3-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="837d3-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="837d3-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="837d3-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="837d3-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="837d3-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="837d3-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="837d3-116">See also</span></span>

- [<span data-ttu-id="837d3-117">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="837d3-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="837d3-118">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="837d3-118">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)

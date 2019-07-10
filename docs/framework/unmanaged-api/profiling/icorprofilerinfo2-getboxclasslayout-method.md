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
ms.openlocfilehash: 0d00c28862036c21c44f46c23fb09e947628dcf3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783042"
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a><span data-ttu-id="3906a-102">Metodo ICorProfilerInfo2::GetBoxClassLayout</span><span class="sxs-lookup"><span data-stu-id="3906a-102">ICorProfilerInfo2::GetBoxClassLayout Method</span></span>
<span data-ttu-id="3906a-103">Ottiene informazioni su dove si trova il tipo di valore specificato quando è sottoposto a boxing.</span><span class="sxs-lookup"><span data-stu-id="3906a-103">Gets information about where the specified value type is located when it is boxed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3906a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3906a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3906a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3906a-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="3906a-106">[in] L'ID della classe che descrive il tipo di valore boxed.</span><span class="sxs-lookup"><span data-stu-id="3906a-106">[in] The ID of the class that describes the value type that is boxed.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="3906a-107">[out] Valore intero che rappresenta l'offset, relativo al puntatore, ID di oggetto boxed del tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="3906a-107">[out] An integer that is the offset, relative to the boxed object ID pointer, of the value type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3906a-108">Note</span><span class="sxs-lookup"><span data-stu-id="3906a-108">Remarks</span></span>  
 <span data-ttu-id="3906a-109">Il `pBufferOffset` valore rappresenta il percorso del tipo di valore all'interno di una finestra.</span><span class="sxs-lookup"><span data-stu-id="3906a-109">The `pBufferOffset` value is the location of the value type within a box.</span></span> <span data-ttu-id="3906a-110">Dopo aver `pBufferOffset` viene applicato a un oggetto sottoposto a conversione boxing, layout di classe del tipo di valore può essere utilizzato per interpretare il valore dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="3906a-110">After `pBufferOffset` is applied to a boxed object, the value type's class layout can be used to interpret the object's value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3906a-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3906a-111">Requirements</span></span>  
 <span data-ttu-id="3906a-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3906a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3906a-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3906a-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3906a-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3906a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3906a-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3906a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3906a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3906a-116">See also</span></span>

- [<span data-ttu-id="3906a-117">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="3906a-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="3906a-118">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="3906a-118">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)

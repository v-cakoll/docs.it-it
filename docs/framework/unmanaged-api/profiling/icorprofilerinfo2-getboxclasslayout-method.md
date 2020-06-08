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
ms.openlocfilehash: 630b67a64716f26577bbc376970e4f76216f4da5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497353"
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a><span data-ttu-id="fc42f-102">Metodo ICorProfilerInfo2::GetBoxClassLayout</span><span class="sxs-lookup"><span data-stu-id="fc42f-102">ICorProfilerInfo2::GetBoxClassLayout Method</span></span>
<span data-ttu-id="fc42f-103">Ottiene informazioni sul punto in cui si trova il tipo di valore specificato quando viene sottoposto a Boxing.</span><span class="sxs-lookup"><span data-stu-id="fc42f-103">Gets information about where the specified value type is located when it is boxed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc42f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fc42f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc42f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fc42f-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="fc42f-106">in ID della classe che descrive il tipo di valore boxed.</span><span class="sxs-lookup"><span data-stu-id="fc42f-106">[in] The ID of the class that describes the value type that is boxed.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="fc42f-107">out Intero che rappresenta l'offset, relativo al puntatore ID oggetto boxed, del tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="fc42f-107">[out] An integer that is the offset, relative to the boxed object ID pointer, of the value type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc42f-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="fc42f-108">Remarks</span></span>  
 <span data-ttu-id="fc42f-109">Il `pBufferOffset` valore è il percorso del tipo di valore all'interno di una casella.</span><span class="sxs-lookup"><span data-stu-id="fc42f-109">The `pBufferOffset` value is the location of the value type within a box.</span></span> <span data-ttu-id="fc42f-110">Dopo che `pBufferOffset` è stato applicato a un oggetto boxed, il layout della classe del tipo di valore può essere utilizzato per interpretare il valore dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="fc42f-110">After `pBufferOffset` is applied to a boxed object, the value type's class layout can be used to interpret the object's value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc42f-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fc42f-111">Requirements</span></span>  
 <span data-ttu-id="fc42f-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc42f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc42f-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fc42f-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fc42f-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc42f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc42f-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc42f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc42f-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc42f-116">See also</span></span>

- [<span data-ttu-id="fc42f-117">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="fc42f-117">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="fc42f-118">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="fc42f-118">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)

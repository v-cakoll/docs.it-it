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
ms.openlocfilehash: 500cf74c320438fc1b78f0aac737b418716e1a11
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862828"
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a><span data-ttu-id="99418-102">Metodo ICorProfilerInfo2::GetBoxClassLayout</span><span class="sxs-lookup"><span data-stu-id="99418-102">ICorProfilerInfo2::GetBoxClassLayout Method</span></span>
<span data-ttu-id="99418-103">Ottiene informazioni sul punto in cui si trova il tipo di valore specificato quando viene sottoposto a Boxing.</span><span class="sxs-lookup"><span data-stu-id="99418-103">Gets information about where the specified value type is located when it is boxed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99418-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="99418-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99418-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="99418-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="99418-106">in ID della classe che descrive il tipo di valore boxed.</span><span class="sxs-lookup"><span data-stu-id="99418-106">[in] The ID of the class that describes the value type that is boxed.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="99418-107">out Intero che rappresenta l'offset, relativo al puntatore ID oggetto boxed, del tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="99418-107">[out] An integer that is the offset, relative to the boxed object ID pointer, of the value type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99418-108">Note</span><span class="sxs-lookup"><span data-stu-id="99418-108">Remarks</span></span>  
 <span data-ttu-id="99418-109">Il valore `pBufferOffset` è il percorso del tipo di valore all'interno di una casella.</span><span class="sxs-lookup"><span data-stu-id="99418-109">The `pBufferOffset` value is the location of the value type within a box.</span></span> <span data-ttu-id="99418-110">Dopo l'applicazione di `pBufferOffset` a un oggetto boxed, il layout della classe del tipo di valore può essere utilizzato per interpretare il valore dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="99418-110">After `pBufferOffset` is applied to a boxed object, the value type's class layout can be used to interpret the object's value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99418-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="99418-111">Requirements</span></span>  
 <span data-ttu-id="99418-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99418-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99418-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="99418-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="99418-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99418-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99418-115">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99418-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99418-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99418-116">See also</span></span>

- [<span data-ttu-id="99418-117">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="99418-117">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="99418-118">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="99418-118">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)

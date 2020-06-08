---
title: Metodo ICorProfilerModuleEnum::Skip
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.Skip Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerModuleEnum interface [.NET Framework profiling]
- ICorProfilerModuleEnum::Skip method [.NET Framework profiling]
ms.assetid: 8dc29c6a-e2ba-41d8-a1e0-0fdd21421e0b
topic_type:
- apiref
ms.openlocfilehash: b48b782b7c8be35bfb815d72758f0bc316fb2114
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84494722"
---
# <a name="icorprofilermoduleenumskip-method"></a><span data-ttu-id="37e3b-102">Metodo ICorProfilerModuleEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="37e3b-102">ICorProfilerModuleEnum::Skip Method</span></span>
<span data-ttu-id="37e3b-103">Sposta in avanti il cursore dell'enumeratore dalla posizione corrente, in modo che venga ignorato il numero specificato di elementi.</span><span class="sxs-lookup"><span data-stu-id="37e3b-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37e3b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="37e3b-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip([in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37e3b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="37e3b-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="37e3b-106">in Numero di elementi da ignorare.</span><span class="sxs-lookup"><span data-stu-id="37e3b-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="37e3b-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="37e3b-107">Return Value</span></span>  
 <span data-ttu-id="37e3b-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="37e3b-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="37e3b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="37e3b-109">HRESULT</span></span>|<span data-ttu-id="37e3b-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37e3b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="37e3b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="37e3b-111">S_OK</span></span>|<span data-ttu-id="37e3b-112">`celt`gli elementi sono stati ignorati.</span><span class="sxs-lookup"><span data-stu-id="37e3b-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="37e3b-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="37e3b-113">S_FALSE</span></span>|<span data-ttu-id="37e3b-114">`celt`Sono stati ignorati meno di elementi, a indicare che non sono presenti altri elementi.</span><span class="sxs-lookup"><span data-stu-id="37e3b-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37e3b-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="37e3b-115">Remarks</span></span>  
 <span data-ttu-id="37e3b-116">La nuova posizione del cursore di questo enumeratore è (posizione corrente) + `celt` .</span><span class="sxs-lookup"><span data-stu-id="37e3b-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37e3b-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="37e3b-117">Requirements</span></span>  
 <span data-ttu-id="37e3b-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37e3b-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37e3b-119">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="37e3b-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="37e3b-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37e3b-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37e3b-121">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37e3b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37e3b-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37e3b-122">See also</span></span>

- [<span data-ttu-id="37e3b-123">Interfaccia ICorProfilerModuleEnum</span><span class="sxs-lookup"><span data-stu-id="37e3b-123">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="37e3b-124">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="37e3b-124">Profiling Interfaces</span></span>](profiling-interfaces.md)

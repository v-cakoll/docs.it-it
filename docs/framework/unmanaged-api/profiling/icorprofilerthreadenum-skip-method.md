---
title: Metodo ICorProfilerThreadEnum::Skip
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Skip
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Skip method [.NET Framework profiling]
ms.assetid: acb8b029-4a96-4ed7-ae3c-310204e5ceea
topic_type:
- apiref
ms.openlocfilehash: b08a501f7d55fbb193afd8c297ca7725348dac76
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76860930"
---
# <a name="icorprofilerthreadenumskip-method"></a><span data-ttu-id="60ad8-102">Metodo ICorProfilerThreadEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="60ad8-102">ICorProfilerThreadEnum::Skip Method</span></span>
<span data-ttu-id="60ad8-103">Sposta in avanti il cursore dell'enumeratore dalla posizione corrente, in modo che venga ignorato il numero specificato di elementi.</span><span class="sxs-lookup"><span data-stu-id="60ad8-103">Advances the enumerator's cursor from its current position to skip the specified number of elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60ad8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="60ad8-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60ad8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="60ad8-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="60ad8-106">in Numero di elementi da ignorare.</span><span class="sxs-lookup"><span data-stu-id="60ad8-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="60ad8-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="60ad8-107">Return Value</span></span>  
 <span data-ttu-id="60ad8-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="60ad8-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="60ad8-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="60ad8-109">HRESULT</span></span>|<span data-ttu-id="60ad8-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="60ad8-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="60ad8-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="60ad8-111">S_OK</span></span>|<span data-ttu-id="60ad8-112">gli elementi `celt` sono stati ignorati.</span><span class="sxs-lookup"><span data-stu-id="60ad8-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="60ad8-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="60ad8-113">S_FALSE</span></span>|<span data-ttu-id="60ad8-114">Sono stati ignorati meno di `celt` elementi, a indicare che non sono presenti altri elementi.</span><span class="sxs-lookup"><span data-stu-id="60ad8-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60ad8-115">Note</span><span class="sxs-lookup"><span data-stu-id="60ad8-115">Remarks</span></span>  
 <span data-ttu-id="60ad8-116">La nuova posizione del cursore di questo enumeratore è (posizione corrente) + `celt`.</span><span class="sxs-lookup"><span data-stu-id="60ad8-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60ad8-117">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="60ad8-117">Requirements</span></span>  
 <span data-ttu-id="60ad8-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60ad8-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60ad8-119">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="60ad8-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="60ad8-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60ad8-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60ad8-121">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60ad8-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60ad8-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60ad8-122">See also</span></span>

- [<span data-ttu-id="60ad8-123">Interfaccia ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="60ad8-123">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="60ad8-124">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="60ad8-124">Profiling Interfaces</span></span>](profiling-interfaces.md)

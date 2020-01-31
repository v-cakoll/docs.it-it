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
ms.openlocfilehash: fb7a2a6d8bac7e9a67a5275694fc07e0f1d469e1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861333"
---
# <a name="icorprofilermoduleenumskip-method"></a><span data-ttu-id="a5ab5-102">Metodo ICorProfilerModuleEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="a5ab5-102">ICorProfilerModuleEnum::Skip Method</span></span>
<span data-ttu-id="a5ab5-103">Sposta in avanti il cursore dell'enumeratore dalla posizione corrente, in modo che venga ignorato il numero specificato di elementi.</span><span class="sxs-lookup"><span data-stu-id="a5ab5-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5ab5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a5ab5-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip([in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5ab5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a5ab5-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="a5ab5-106">in Numero di elementi da ignorare.</span><span class="sxs-lookup"><span data-stu-id="a5ab5-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a5ab5-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a5ab5-107">Return Value</span></span>  
 <span data-ttu-id="a5ab5-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="a5ab5-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a5ab5-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a5ab5-109">HRESULT</span></span>|<span data-ttu-id="a5ab5-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a5ab5-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a5ab5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a5ab5-111">S_OK</span></span>|<span data-ttu-id="a5ab5-112">gli elementi `celt` sono stati ignorati.</span><span class="sxs-lookup"><span data-stu-id="a5ab5-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="a5ab5-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a5ab5-113">S_FALSE</span></span>|<span data-ttu-id="a5ab5-114">Sono stati ignorati meno di `celt` elementi, a indicare che non sono presenti altri elementi.</span><span class="sxs-lookup"><span data-stu-id="a5ab5-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5ab5-115">Note</span><span class="sxs-lookup"><span data-stu-id="a5ab5-115">Remarks</span></span>  
 <span data-ttu-id="a5ab5-116">La nuova posizione del cursore di questo enumeratore è (posizione corrente) + `celt`.</span><span class="sxs-lookup"><span data-stu-id="a5ab5-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5ab5-117">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="a5ab5-117">Requirements</span></span>  
 <span data-ttu-id="a5ab5-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5ab5-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5ab5-119">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a5ab5-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a5ab5-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5ab5-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5ab5-121">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5ab5-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5ab5-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5ab5-122">See also</span></span>

- [<span data-ttu-id="a5ab5-123">Interfaccia ICorProfilerModuleEnum</span><span class="sxs-lookup"><span data-stu-id="a5ab5-123">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="a5ab5-124">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="a5ab5-124">Profiling Interfaces</span></span>](profiling-interfaces.md)

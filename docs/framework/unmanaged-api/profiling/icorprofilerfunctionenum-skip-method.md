---
title: Metodo ICorProfilerFunctionEnum::Skip
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Skip Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
- ICorProfilerFunctionEnum::Skip method [.NET Framework profiling]
ms.assetid: 051465b9-e479-494a-804b-c880323b4cbe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ba1f357c0d68b5a8b5104569a95433504cc84ee6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54675335"
---
# <a name="icorprofilerfunctionenumskip-method"></a><span data-ttu-id="c7ba3-102">Metodo ICorProfilerFunctionEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="c7ba3-102">ICorProfilerFunctionEnum::Skip Method</span></span>
<span data-ttu-id="c7ba3-103">Sposta in avanti il cursore dell'enumeratore dalla posizione corrente, in modo che venga ignorato il numero specificato di elementi.</span><span class="sxs-lookup"><span data-stu-id="c7ba3-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7ba3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c7ba3-104">Syntax</span></span>  
  
```  
HRESULT Skip([in] ULONG celt);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c7ba3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c7ba3-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="c7ba3-106">[in] Il numero di elementi da ignorare.</span><span class="sxs-lookup"><span data-stu-id="c7ba3-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c7ba3-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c7ba3-107">Return Value</span></span>  
 <span data-ttu-id="c7ba3-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="c7ba3-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c7ba3-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c7ba3-109">HRESULT</span></span>|<span data-ttu-id="c7ba3-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c7ba3-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c7ba3-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c7ba3-111">S_OK</span></span>|<span data-ttu-id="c7ba3-112">`celt` gli elementi sono stati ignorati.</span><span class="sxs-lookup"><span data-stu-id="c7ba3-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="c7ba3-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="c7ba3-113">S_FALSE</span></span>|<span data-ttu-id="c7ba3-114">Meno di `celt` elementi sono stati ignorati, che indica che non sono presenti più elementi.</span><span class="sxs-lookup"><span data-stu-id="c7ba3-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7ba3-115">Note</span><span class="sxs-lookup"><span data-stu-id="c7ba3-115">Remarks</span></span>  
 <span data-ttu-id="c7ba3-116">La nuova posizione del cursore dell'enumeratore, questa viene (posizione corrente) + `celt`.</span><span class="sxs-lookup"><span data-stu-id="c7ba3-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7ba3-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c7ba3-117">Requirements</span></span>  
 <span data-ttu-id="c7ba3-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7ba3-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7ba3-119">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c7ba3-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c7ba3-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7ba3-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7ba3-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7ba3-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7ba3-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7ba3-122">See also</span></span>
- [<span data-ttu-id="c7ba3-123">Interfaccia ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="c7ba3-123">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="c7ba3-124">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="c7ba3-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)

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
ms.openlocfilehash: d2a0bff0d3d93ab8542699cffd3d0ecc032246ad
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448205"
---
# <a name="icorprofilerfunctionenumskip-method"></a><span data-ttu-id="dce2f-102">Metodo ICorProfilerFunctionEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="dce2f-102">ICorProfilerFunctionEnum::Skip Method</span></span>
<span data-ttu-id="dce2f-103">Sposta in avanti il cursore dell'enumeratore dalla posizione corrente, in modo che venga ignorato il numero specificato di elementi.</span><span class="sxs-lookup"><span data-stu-id="dce2f-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dce2f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dce2f-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip([in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dce2f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dce2f-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="dce2f-106">in Numero di elementi da ignorare.</span><span class="sxs-lookup"><span data-stu-id="dce2f-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dce2f-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="dce2f-107">Return Value</span></span>  
 <span data-ttu-id="dce2f-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="dce2f-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="dce2f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dce2f-109">HRESULT</span></span>|<span data-ttu-id="dce2f-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dce2f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dce2f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="dce2f-111">S_OK</span></span>|<span data-ttu-id="dce2f-112">gli elementi `celt` sono stati ignorati.</span><span class="sxs-lookup"><span data-stu-id="dce2f-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="dce2f-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="dce2f-113">S_FALSE</span></span>|<span data-ttu-id="dce2f-114">Sono stati ignorati meno di `celt` elementi, a indicare che non sono presenti altri elementi.</span><span class="sxs-lookup"><span data-stu-id="dce2f-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dce2f-115">Note</span><span class="sxs-lookup"><span data-stu-id="dce2f-115">Remarks</span></span>  
 <span data-ttu-id="dce2f-116">La nuova posizione del cursore di questo enumeratore è (posizione corrente) + `celt`.</span><span class="sxs-lookup"><span data-stu-id="dce2f-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dce2f-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dce2f-117">Requirements</span></span>  
 <span data-ttu-id="dce2f-118">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dce2f-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dce2f-119">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dce2f-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dce2f-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dce2f-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dce2f-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dce2f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dce2f-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dce2f-122">See also</span></span>

- [<span data-ttu-id="dce2f-123">Interfaccia ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="dce2f-123">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="dce2f-124">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="dce2f-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)

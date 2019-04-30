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
ms.openlocfilehash: f0e334c75afee60591db2b4e1f45cf0ec753ee2e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992056"
---
# <a name="icorprofilerfunctionenumskip-method"></a><span data-ttu-id="5a7cf-102">Metodo ICorProfilerFunctionEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="5a7cf-102">ICorProfilerFunctionEnum::Skip Method</span></span>
<span data-ttu-id="5a7cf-103">Sposta in avanti il cursore dell'enumeratore dalla posizione corrente, in modo che venga ignorato il numero specificato di elementi.</span><span class="sxs-lookup"><span data-stu-id="5a7cf-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a7cf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5a7cf-104">Syntax</span></span>  
  
```  
HRESULT Skip([in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a7cf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5a7cf-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="5a7cf-106">[in] Il numero di elementi da ignorare.</span><span class="sxs-lookup"><span data-stu-id="5a7cf-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a7cf-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5a7cf-107">Return Value</span></span>  
 <span data-ttu-id="5a7cf-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="5a7cf-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5a7cf-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5a7cf-109">HRESULT</span></span>|<span data-ttu-id="5a7cf-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5a7cf-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5a7cf-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5a7cf-111">S_OK</span></span>|<span data-ttu-id="5a7cf-112">`celt` gli elementi sono stati ignorati.</span><span class="sxs-lookup"><span data-stu-id="5a7cf-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="5a7cf-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="5a7cf-113">S_FALSE</span></span>|<span data-ttu-id="5a7cf-114">Meno di `celt` elementi sono stati ignorati, che indica che non sono presenti più elementi.</span><span class="sxs-lookup"><span data-stu-id="5a7cf-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a7cf-115">Note</span><span class="sxs-lookup"><span data-stu-id="5a7cf-115">Remarks</span></span>  
 <span data-ttu-id="5a7cf-116">La nuova posizione del cursore dell'enumeratore, questa viene (posizione corrente) + `celt`.</span><span class="sxs-lookup"><span data-stu-id="5a7cf-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a7cf-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5a7cf-117">Requirements</span></span>  
 <span data-ttu-id="5a7cf-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a7cf-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a7cf-119">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5a7cf-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5a7cf-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a7cf-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a7cf-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a7cf-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a7cf-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a7cf-122">See also</span></span>

- [<span data-ttu-id="5a7cf-123">Interfaccia ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="5a7cf-123">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="5a7cf-124">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="5a7cf-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)

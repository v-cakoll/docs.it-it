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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eecb2a5da9dddaccbab7fcc6d74af6e4c6bfb72c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775136"
---
# <a name="icorprofilermoduleenumskip-method"></a><span data-ttu-id="0470c-102">Metodo ICorProfilerModuleEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="0470c-102">ICorProfilerModuleEnum::Skip Method</span></span>
<span data-ttu-id="0470c-103">Sposta in avanti il cursore dell'enumeratore dalla posizione corrente, in modo che venga ignorato il numero specificato di elementi.</span><span class="sxs-lookup"><span data-stu-id="0470c-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0470c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0470c-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip([in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0470c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0470c-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="0470c-106">[in] Il numero di elementi da ignorare.</span><span class="sxs-lookup"><span data-stu-id="0470c-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0470c-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0470c-107">Return Value</span></span>  
 <span data-ttu-id="0470c-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="0470c-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="0470c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0470c-109">HRESULT</span></span>|<span data-ttu-id="0470c-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0470c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0470c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0470c-111">S_OK</span></span>|<span data-ttu-id="0470c-112">`celt` gli elementi sono stati ignorati.</span><span class="sxs-lookup"><span data-stu-id="0470c-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="0470c-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="0470c-113">S_FALSE</span></span>|<span data-ttu-id="0470c-114">Meno di `celt` elementi sono stati ignorati, che indica che non sono presenti più elementi.</span><span class="sxs-lookup"><span data-stu-id="0470c-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0470c-115">Note</span><span class="sxs-lookup"><span data-stu-id="0470c-115">Remarks</span></span>  
 <span data-ttu-id="0470c-116">La nuova posizione del cursore dell'enumeratore, questa viene (posizione corrente) + `celt`.</span><span class="sxs-lookup"><span data-stu-id="0470c-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0470c-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0470c-117">Requirements</span></span>  
 <span data-ttu-id="0470c-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0470c-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0470c-119">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0470c-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0470c-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0470c-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0470c-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0470c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0470c-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0470c-122">See also</span></span>

- [<span data-ttu-id="0470c-123">Interfaccia ICorProfilerModuleEnum</span><span class="sxs-lookup"><span data-stu-id="0470c-123">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="0470c-124">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="0470c-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)

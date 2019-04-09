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
ms.openlocfilehash: 397e8afcc176bcd9733e83dc6425fe49f385931e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078202"
---
# <a name="icorprofilermoduleenumskip-method"></a><span data-ttu-id="8f7e9-102">Metodo ICorProfilerModuleEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="8f7e9-102">ICorProfilerModuleEnum::Skip Method</span></span>
<span data-ttu-id="8f7e9-103">Sposta in avanti il cursore dell'enumeratore dalla posizione corrente, in modo che venga ignorato il numero specificato di elementi.</span><span class="sxs-lookup"><span data-stu-id="8f7e9-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f7e9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8f7e9-104">Syntax</span></span>  
  
```  
HRESULT Skip([in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f7e9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8f7e9-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="8f7e9-106">[in] Il numero di elementi da ignorare.</span><span class="sxs-lookup"><span data-stu-id="8f7e9-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8f7e9-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8f7e9-107">Return Value</span></span>  
 <span data-ttu-id="8f7e9-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="8f7e9-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="8f7e9-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8f7e9-109">HRESULT</span></span>|<span data-ttu-id="8f7e9-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8f7e9-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8f7e9-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="8f7e9-111">S_OK</span></span>|`celt` <span data-ttu-id="8f7e9-112">gli elementi sono stati ignorati.</span><span class="sxs-lookup"><span data-stu-id="8f7e9-112">elements were skipped.</span></span>|  
|<span data-ttu-id="8f7e9-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="8f7e9-113">S_FALSE</span></span>|<span data-ttu-id="8f7e9-114">Meno di `celt` elementi sono stati ignorati, che indica che non sono presenti più elementi.</span><span class="sxs-lookup"><span data-stu-id="8f7e9-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f7e9-115">Note</span><span class="sxs-lookup"><span data-stu-id="8f7e9-115">Remarks</span></span>  
 <span data-ttu-id="8f7e9-116">La nuova posizione del cursore dell'enumeratore, questa viene (posizione corrente) + `celt`.</span><span class="sxs-lookup"><span data-stu-id="8f7e9-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f7e9-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8f7e9-117">Requirements</span></span>  
 <span data-ttu-id="8f7e9-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f7e9-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f7e9-119">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8f7e9-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8f7e9-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f7e9-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="8f7e9-121">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="8f7e9-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8f7e9-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f7e9-122">See also</span></span>

- [<span data-ttu-id="8f7e9-123">Interfaccia ICorProfilerModuleEnum</span><span class="sxs-lookup"><span data-stu-id="8f7e9-123">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="8f7e9-124">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="8f7e9-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)

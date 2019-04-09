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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cce96e8c6d046beba9e45c7121bf68444fd51c95
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173342"
---
# <a name="icorprofilerthreadenumskip-method"></a><span data-ttu-id="83671-102">Metodo ICorProfilerThreadEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="83671-102">ICorProfilerThreadEnum::Skip Method</span></span>
<span data-ttu-id="83671-103">Sposta in avanti il cursore dell'enumeratore dalla posizione corrente, in modo che venga ignorato il numero specificato di elementi.</span><span class="sxs-lookup"><span data-stu-id="83671-103">Advances the enumerator's cursor from its current position to skip the specified number of elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83671-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="83671-104">Syntax</span></span>  
  
```  
HRESULT Skip (    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83671-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="83671-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="83671-106">[in] Il numero di elementi da ignorare.</span><span class="sxs-lookup"><span data-stu-id="83671-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83671-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="83671-107">Return Value</span></span>  
 <span data-ttu-id="83671-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="83671-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="83671-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="83671-109">HRESULT</span></span>|<span data-ttu-id="83671-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="83671-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="83671-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="83671-111">S_OK</span></span>|`celt` <span data-ttu-id="83671-112">gli elementi sono stati ignorati.</span><span class="sxs-lookup"><span data-stu-id="83671-112">elements were skipped.</span></span>|  
|<span data-ttu-id="83671-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="83671-113">S_FALSE</span></span>|<span data-ttu-id="83671-114">Meno di `celt` elementi sono stati ignorati, che indica che non sono presenti più elementi.</span><span class="sxs-lookup"><span data-stu-id="83671-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83671-115">Note</span><span class="sxs-lookup"><span data-stu-id="83671-115">Remarks</span></span>  
 <span data-ttu-id="83671-116">La nuova posizione del cursore dell'enumeratore, questa viene (posizione corrente) + `celt`.</span><span class="sxs-lookup"><span data-stu-id="83671-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83671-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="83671-117">Requirements</span></span>  
 <span data-ttu-id="83671-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83671-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83671-119">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="83671-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="83671-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83671-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="83671-121">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="83671-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="83671-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83671-122">See also</span></span>

- [<span data-ttu-id="83671-123">Interfaccia ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="83671-123">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="83671-124">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="83671-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)

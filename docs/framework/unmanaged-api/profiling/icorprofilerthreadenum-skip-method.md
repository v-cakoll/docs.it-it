---
title: Metodo ICorProfilerThreadEnum::Skip
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerThreadEnum.Skip
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerThreadEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Skip method [.NET Framework profiling]
ms.assetid: acb8b029-4a96-4ed7-ae3c-310204e5ceea
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f492a455165f3b49994beb3220334e2932bf214c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerthreadenumskip-method"></a><span data-ttu-id="abcda-102">Metodo ICorProfilerThreadEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="abcda-102">ICorProfilerThreadEnum::Skip Method</span></span>
<span data-ttu-id="abcda-103">Sposta in avanti il cursore dell'enumeratore dalla posizione corrente, in modo che venga ignorato il numero specificato di elementi.</span><span class="sxs-lookup"><span data-stu-id="abcda-103">Advances the enumerator's cursor from its current position to skip the specified number of elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abcda-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="abcda-104">Syntax</span></span>  
  
```  
HRESULT Skip (    [in] ULONG celt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="abcda-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="abcda-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="abcda-106">[in] Il numero di elementi da ignorare.</span><span class="sxs-lookup"><span data-stu-id="abcda-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="abcda-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="abcda-107">Return Value</span></span>  
 <span data-ttu-id="abcda-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="abcda-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="abcda-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="abcda-109">HRESULT</span></span>|<span data-ttu-id="abcda-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="abcda-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="abcda-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="abcda-111">S_OK</span></span>|<span data-ttu-id="abcda-112">`celt`gli elementi sono stati ignorati.</span><span class="sxs-lookup"><span data-stu-id="abcda-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="abcda-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="abcda-113">S_FALSE</span></span>|<span data-ttu-id="abcda-114">Meno di `celt` elementi ignorati, a indicare che non sono presenti più elementi.</span><span class="sxs-lookup"><span data-stu-id="abcda-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="abcda-115">Note</span><span class="sxs-lookup"><span data-stu-id="abcda-115">Remarks</span></span>  
 <span data-ttu-id="abcda-116">La nuova posizione del cursore dell'enumeratore, questo viene (posizione corrente) + `celt`.</span><span class="sxs-lookup"><span data-stu-id="abcda-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abcda-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="abcda-117">Requirements</span></span>  
 <span data-ttu-id="abcda-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="abcda-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abcda-119">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="abcda-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="abcda-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="abcda-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="abcda-121">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abcda-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abcda-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="abcda-122">See Also</span></span>  
 [<span data-ttu-id="abcda-123">ICorProfilerThreadEnum (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="abcda-123">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 [<span data-ttu-id="abcda-124">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="abcda-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)

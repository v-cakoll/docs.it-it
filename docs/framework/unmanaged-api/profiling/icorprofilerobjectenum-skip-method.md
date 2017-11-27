---
title: Metodo ICorProfilerObjectEnum::Skip
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerObjectEnum.Skip
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerObjectEnum::Skip
helpviewer_keywords:
- ICorProfilerObjectEnum::Skip method [.NET Framework profiling]
- Skip method, ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: f8e498f8-f93a-4b82-bd22-55bdbf5e8d45
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 84960af6e128f3a6aa9e3b45187e282ac7228e0f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerobjectenumskip-method"></a><span data-ttu-id="362d2-102">Metodo ICorProfilerObjectEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="362d2-102">ICorProfilerObjectEnum::Skip Method</span></span>
<span data-ttu-id="362d2-103">Sposta il cursore dell'enumeratore dalla posizione corrente in modo che venga ignorato il numero specificato di elementi.</span><span class="sxs-lookup"><span data-stu-id="362d2-103">Advances the cursor of this enumerator from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="362d2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="362d2-104">Syntax</span></span>  
  
```  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="362d2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="362d2-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="362d2-106">[in] Il numero di elementi da ignorare.</span><span class="sxs-lookup"><span data-stu-id="362d2-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="362d2-107">Note</span><span class="sxs-lookup"><span data-stu-id="362d2-107">Remarks</span></span>  
 <span data-ttu-id="362d2-108">La nuova posizione del cursore dell'enumeratore questo: (posizione corrente) + `celt` .</span><span class="sxs-lookup"><span data-stu-id="362d2-108">The new position of this enumerator's cursor is: (current position) + `celt` .</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="362d2-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="362d2-109">Requirements</span></span>  
 <span data-ttu-id="362d2-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="362d2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="362d2-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="362d2-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="362d2-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="362d2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="362d2-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="362d2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="362d2-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="362d2-114">See Also</span></span>  
 [<span data-ttu-id="362d2-115">ICorProfilerObjectEnum (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="362d2-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)

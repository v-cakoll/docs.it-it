---
title: Metodo ICorProfilerObjectEnum::Skip
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Skip
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Skip
helpviewer_keywords:
- ICorProfilerObjectEnum::Skip method [.NET Framework profiling]
- Skip method, ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: f8e498f8-f93a-4b82-bd22-55bdbf5e8d45
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2f1e12e59eefece1aa3a2a2294b34f5cee7c700c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54543107"
---
# <a name="icorprofilerobjectenumskip-method"></a><span data-ttu-id="eae98-102">Metodo ICorProfilerObjectEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="eae98-102">ICorProfilerObjectEnum::Skip Method</span></span>
<span data-ttu-id="eae98-103">Sposta il cursore dell'enumeratore dalla posizione corrente in modo che venga ignorato il numero specificato di elementi.</span><span class="sxs-lookup"><span data-stu-id="eae98-103">Advances the cursor of this enumerator from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eae98-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eae98-104">Syntax</span></span>  
  
```  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eae98-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="eae98-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="eae98-106">[in] Il numero di elementi da ignorare.</span><span class="sxs-lookup"><span data-stu-id="eae98-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eae98-107">Note</span><span class="sxs-lookup"><span data-stu-id="eae98-107">Remarks</span></span>  
 <span data-ttu-id="eae98-108">La nuova posizione del cursore dell'enumeratore, questo è: (posizione corrente) + `celt` .</span><span class="sxs-lookup"><span data-stu-id="eae98-108">The new position of this enumerator's cursor is: (current position) + `celt` .</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eae98-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="eae98-109">Requirements</span></span>  
 <span data-ttu-id="eae98-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eae98-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eae98-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="eae98-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="eae98-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eae98-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eae98-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eae98-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eae98-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eae98-114">See also</span></span>
- [<span data-ttu-id="eae98-115">Interfaccia ICorProfilerObjectEnum</span><span class="sxs-lookup"><span data-stu-id="eae98-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)

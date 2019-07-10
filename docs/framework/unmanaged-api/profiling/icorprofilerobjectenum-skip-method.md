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
ms.openlocfilehash: b5818cb8d7da7415feb61532799df5fa5a16fd3b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781220"
---
# <a name="icorprofilerobjectenumskip-method"></a><span data-ttu-id="009aa-102">Metodo ICorProfilerObjectEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="009aa-102">ICorProfilerObjectEnum::Skip Method</span></span>
<span data-ttu-id="009aa-103">Sposta il cursore dell'enumeratore dalla posizione corrente in modo che venga ignorato il numero specificato di elementi.</span><span class="sxs-lookup"><span data-stu-id="009aa-103">Advances the cursor of this enumerator from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="009aa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="009aa-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="009aa-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="009aa-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="009aa-106">[in] Il numero di elementi da ignorare.</span><span class="sxs-lookup"><span data-stu-id="009aa-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="009aa-107">Note</span><span class="sxs-lookup"><span data-stu-id="009aa-107">Remarks</span></span>  
 <span data-ttu-id="009aa-108">La nuova posizione del cursore dell'enumeratore, questo è: (posizione corrente) + `celt` .</span><span class="sxs-lookup"><span data-stu-id="009aa-108">The new position of this enumerator's cursor is: (current position) + `celt` .</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="009aa-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="009aa-109">Requirements</span></span>  
 <span data-ttu-id="009aa-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="009aa-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="009aa-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="009aa-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="009aa-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="009aa-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="009aa-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="009aa-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="009aa-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="009aa-114">See also</span></span>

- [<span data-ttu-id="009aa-115">Interfaccia ICorProfilerObjectEnum</span><span class="sxs-lookup"><span data-stu-id="009aa-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)

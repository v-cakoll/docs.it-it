---
title: Metodo ICorProfilerThreadEnum::GetCount
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.GetCount
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::GetCount
helpviewer_keywords:
- ICorProfilerThreadEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: d6dbdc4a-6115-455d-a3f3-704a81d3646b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aaec45018261cd9318f65c26eec6ab89b437c3fa
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499004"
---
# <a name="icorprofilerthreadenumgetcount-method"></a><span data-ttu-id="2904d-102">Metodo ICorProfilerThreadEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="2904d-102">ICorProfilerThreadEnum::GetCount Method</span></span>
<span data-ttu-id="2904d-103">Ottiene il numero di thread usati dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2904d-103">Gets the number of threads that are used by the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2904d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2904d-104">Syntax</span></span>  
  
```  
HRESULT GetCount (    [out] ULONG * pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2904d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2904d-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="2904d-106">[out] Il numero di thread utilizzati dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2904d-106">[out] The number of threads used by the application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2904d-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2904d-107">Requirements</span></span>  
 <span data-ttu-id="2904d-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2904d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2904d-109">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2904d-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2904d-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2904d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2904d-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2904d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2904d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2904d-112">See also</span></span>
- [<span data-ttu-id="2904d-113">Interfaccia ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="2904d-113">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="2904d-114">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="2904d-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)

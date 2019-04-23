---
title: Metodo ICorProfilerFunctionEnum::GetCount
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.GetCount Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::GetCount
helpviewer_keywords:
- ICorProfilerFunctionEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 62ec65e3-3e9d-400b-ae61-d24b8963995b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a5061750489c74e0385f2ce020c88518604b3167
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59169286"
---
# <a name="icorprofilerfunctionenumgetcount-method"></a><span data-ttu-id="18b56-102">Metodo ICorProfilerFunctionEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="18b56-102">ICorProfilerFunctionEnum::GetCount Method</span></span>
<span data-ttu-id="18b56-103">Ottiene il numero di funzioni che sono state caricate dall'applicazione o caricate forzatamente dal profiler.</span><span class="sxs-lookup"><span data-stu-id="18b56-103">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18b56-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="18b56-104">Syntax</span></span>  
  
```  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18b56-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="18b56-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="18b56-106">[out] Il numero di funzioni che sono stati caricati.</span><span class="sxs-lookup"><span data-stu-id="18b56-106">[out] The number of functions that were loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18b56-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="18b56-107">Requirements</span></span>  
 <span data-ttu-id="18b56-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18b56-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18b56-109">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="18b56-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="18b56-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18b56-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18b56-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18b56-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18b56-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18b56-112">See also</span></span>

- [<span data-ttu-id="18b56-113">Interfaccia ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="18b56-113">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="18b56-114">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="18b56-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)

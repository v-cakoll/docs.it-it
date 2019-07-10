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
ms.openlocfilehash: 6403540f9641ce885edf2760370e35f48faf1f10
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780314"
---
# <a name="icorprofilerfunctionenumgetcount-method"></a><span data-ttu-id="952d9-102">Metodo ICorProfilerFunctionEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="952d9-102">ICorProfilerFunctionEnum::GetCount Method</span></span>
<span data-ttu-id="952d9-103">Ottiene il numero di funzioni che sono state caricate dall'applicazione o caricate forzatamente dal profiler.</span><span class="sxs-lookup"><span data-stu-id="952d9-103">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="952d9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="952d9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="952d9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="952d9-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="952d9-106">[out] Il numero di funzioni che sono stati caricati.</span><span class="sxs-lookup"><span data-stu-id="952d9-106">[out] The number of functions that were loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="952d9-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="952d9-107">Requirements</span></span>  
 <span data-ttu-id="952d9-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="952d9-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="952d9-109">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="952d9-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="952d9-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="952d9-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="952d9-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="952d9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="952d9-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="952d9-112">See also</span></span>

- [<span data-ttu-id="952d9-113">Interfaccia ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="952d9-113">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="952d9-114">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="952d9-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)

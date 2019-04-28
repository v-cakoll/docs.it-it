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
ms.openlocfilehash: 8b02f70f22a7d35bf0fe7816a52c490f88b31217
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597128"
---
# <a name="icorprofilerthreadenumgetcount-method"></a><span data-ttu-id="862c2-102">Metodo ICorProfilerThreadEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="862c2-102">ICorProfilerThreadEnum::GetCount Method</span></span>
<span data-ttu-id="862c2-103">Ottiene il numero di thread usati dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="862c2-103">Gets the number of threads that are used by the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="862c2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="862c2-104">Syntax</span></span>  
  
```  
HRESULT GetCount (    [out] ULONG * pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="862c2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="862c2-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="862c2-106">[out] Il numero di thread utilizzati dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="862c2-106">[out] The number of threads used by the application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="862c2-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="862c2-107">Requirements</span></span>  
 <span data-ttu-id="862c2-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="862c2-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="862c2-109">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="862c2-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="862c2-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="862c2-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="862c2-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="862c2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="862c2-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="862c2-112">See also</span></span>

- [<span data-ttu-id="862c2-113">Interfaccia ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="862c2-113">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="862c2-114">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="862c2-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)

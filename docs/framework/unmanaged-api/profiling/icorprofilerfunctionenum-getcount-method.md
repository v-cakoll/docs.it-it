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
ms.openlocfilehash: 8a21f1c0018e99b94a1b9910b6f266bdca84b7fe
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864557"
---
# <a name="icorprofilerfunctionenumgetcount-method"></a><span data-ttu-id="9ce2b-102">Metodo ICorProfilerFunctionEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="9ce2b-102">ICorProfilerFunctionEnum::GetCount Method</span></span>
<span data-ttu-id="9ce2b-103">Ottiene il numero di funzioni che sono state caricate dall'applicazione o caricate forzatamente dal profiler.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-103">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ce2b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9ce2b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ce2b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9ce2b-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="9ce2b-106">out Il numero di funzioni che sono state caricate.</span><span class="sxs-lookup"><span data-stu-id="9ce2b-106">[out] The number of functions that were loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ce2b-107">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="9ce2b-107">Requirements</span></span>  
 <span data-ttu-id="9ce2b-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ce2b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ce2b-109">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9ce2b-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9ce2b-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ce2b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ce2b-111">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ce2b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ce2b-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ce2b-112">See also</span></span>

- [<span data-ttu-id="9ce2b-113">Interfaccia ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="9ce2b-113">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="9ce2b-114">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="9ce2b-114">Profiling Interfaces</span></span>](profiling-interfaces.md)

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
ms.openlocfilehash: 413b860353d3a9e75771f9349ebf151d8f2e3579
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453295"
---
# <a name="icorprofilerfunctionenumgetcount-method"></a><span data-ttu-id="a88ce-102">Metodo ICorProfilerFunctionEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="a88ce-102">ICorProfilerFunctionEnum::GetCount Method</span></span>
<span data-ttu-id="a88ce-103">Ottiene il numero di funzioni che sono state caricate dall'applicazione o caricate forzatamente dal profiler.</span><span class="sxs-lookup"><span data-stu-id="a88ce-103">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a88ce-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a88ce-104">Syntax</span></span>  
  
```  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a88ce-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a88ce-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="a88ce-106">[out] Il numero di funzioni che sono stati caricati.</span><span class="sxs-lookup"><span data-stu-id="a88ce-106">[out] The number of functions that were loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a88ce-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a88ce-107">Requirements</span></span>  
 <span data-ttu-id="a88ce-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a88ce-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a88ce-109">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a88ce-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a88ce-110">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="a88ce-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a88ce-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a88ce-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a88ce-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a88ce-112">See Also</span></span>  
 [<span data-ttu-id="a88ce-113">Interfaccia ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="a88ce-113">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 [<span data-ttu-id="a88ce-114">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="a88ce-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)

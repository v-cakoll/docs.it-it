---
title: Metodo ICorProfilerInfo3::EnumModules
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.EnumModules Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::EnumModules
helpviewer_keywords:
- ICorProfilerInfo3::EnumModules method [.NET Framework profiling]
- EnumModules method [.NET Framework profiling]
ms.assetid: 1bf00b42-69da-4019-91b3-bf88026e83fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8045e689353a047870c1d93022132846f37dc165
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453698"
---
# <a name="icorprofilerinfo3enummodules-method"></a><span data-ttu-id="c959c-102">Metodo ICorProfilerInfo3::EnumModules</span><span class="sxs-lookup"><span data-stu-id="c959c-102">ICorProfilerInfo3::EnumModules Method</span></span>
<span data-ttu-id="c959c-103">Restituisce un enumeratore che fornisce i metodi per scorrere in sequenza una raccolta di moduli gestiti caricati nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c959c-103">Returns an enumerator that provides methods to sequentially iterate through a collection of managed modules that are loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c959c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c959c-104">Syntax</span></span>  
  
```  
HRESULT EnumModules([out] ICorProfilerModuleEnum** ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c959c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c959c-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="c959c-106">[out] Un puntatore a un [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c959c-106">[out] A pointer to an [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c959c-107">Note</span><span class="sxs-lookup"><span data-stu-id="c959c-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c959c-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c959c-108">Requirements</span></span>  
 <span data-ttu-id="c959c-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c959c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c959c-110">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c959c-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c959c-111">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="c959c-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c959c-112">**Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c959c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c959c-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c959c-113">See Also</span></span>  
 [<span data-ttu-id="c959c-114">Interfaccia ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="c959c-114">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 [<span data-ttu-id="c959c-115">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="c959c-115">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="c959c-116">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="c959c-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="c959c-117">Profilatura</span><span class="sxs-lookup"><span data-stu-id="c959c-117">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)

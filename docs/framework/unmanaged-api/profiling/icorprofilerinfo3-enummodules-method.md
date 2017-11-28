---
title: Metodo ICorProfilerInfo3::EnumModules
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.EnumModules Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::EnumModules
helpviewer_keywords:
- ICorProfilerInfo3::EnumModules method [.NET Framework profiling]
- EnumModules method [.NET Framework profiling]
ms.assetid: 1bf00b42-69da-4019-91b3-bf88026e83fb
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: aac765ae29e567965cd90fc9e165d303cc3fa866
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo3enummodules-method"></a><span data-ttu-id="4c7e2-102">Metodo ICorProfilerInfo3::EnumModules</span><span class="sxs-lookup"><span data-stu-id="4c7e2-102">ICorProfilerInfo3::EnumModules Method</span></span>
<span data-ttu-id="4c7e2-103">Restituisce un enumeratore che fornisce i metodi per scorrere in sequenza una raccolta di moduli gestiti caricati nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4c7e2-103">Returns an enumerator that provides methods to sequentially iterate through a collection of managed modules that are loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c7e2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4c7e2-104">Syntax</span></span>  
  
```  
HRESULT EnumModules([out] ICorProfilerModuleEnum** ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4c7e2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4c7e2-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="4c7e2-106">[out] Un puntatore a un [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="4c7e2-106">[out] A pointer to an [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c7e2-107">Note</span><span class="sxs-lookup"><span data-stu-id="4c7e2-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c7e2-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4c7e2-108">Requirements</span></span>  
 <span data-ttu-id="4c7e2-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c7e2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c7e2-110">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4c7e2-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4c7e2-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4c7e2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4c7e2-112">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c7e2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c7e2-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c7e2-113">See Also</span></span>  
 [<span data-ttu-id="4c7e2-114">ICorProfilerFunctionEnum (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="4c7e2-114">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 [<span data-ttu-id="4c7e2-115">ICorProfilerInfo3 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="4c7e2-115">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="4c7e2-116">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="4c7e2-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="4c7e2-117">Profilatura</span><span class="sxs-lookup"><span data-stu-id="4c7e2-117">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)

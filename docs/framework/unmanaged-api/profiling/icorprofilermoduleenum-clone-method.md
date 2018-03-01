---
title: Metodo ICorProfilerModuleEnum::Clone
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerModuleEnum.Clone Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerModuleEnum interface [.NET Framework profiling]
- ICorProfilerModuleEnum::Clone method [.NET Framework profiling]
ms.assetid: 7dec7e36-8d88-416d-b437-abf98b76c1df
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5d6e5da0912c1926fea4afe513e7140055052416
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilermoduleenumclone-method"></a><span data-ttu-id="87b07-102">Metodo ICorProfilerModuleEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="87b07-102">ICorProfilerModuleEnum::Clone Method</span></span>
<span data-ttu-id="87b07-103">Ottiene un puntatore a interfaccia a una copia di questo [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="87b07-103">Gets an interface pointer to a copy of this [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87b07-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="87b07-104">Syntax</span></span>  
  
```  
HRESULT Clone([out] ICorProfilerObjectEnum **ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="87b07-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="87b07-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="87b07-106">[out] Un puntatore a puntatore a interfaccia che a sua volta punta alla copia di questo [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="87b07-106">[out] A pointer to the interface pointer that in turn points to the copy of this [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span> <span data-ttu-id="87b07-107">La copia dell'enumeratore mantiene il proprio stato di enumerazione separatamente da questo enumeratore.</span><span class="sxs-lookup"><span data-stu-id="87b07-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="87b07-108">Tuttavia, posizione iniziale del cursore della copia è quella della posizione corrente del cursore dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="87b07-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87b07-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="87b07-109">Requirements</span></span>  
 <span data-ttu-id="87b07-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87b07-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87b07-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="87b07-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="87b07-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87b07-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87b07-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87b07-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87b07-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87b07-114">See Also</span></span>  
 [<span data-ttu-id="87b07-115">Interfaccia ICorProfilerModuleEnum</span><span class="sxs-lookup"><span data-stu-id="87b07-115">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 [<span data-ttu-id="87b07-116">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="87b07-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)

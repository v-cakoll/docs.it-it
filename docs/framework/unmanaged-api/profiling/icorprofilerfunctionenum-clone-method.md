---
title: Metodo ICorProfilerFunctionEnum::Clone
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
- ICorProfilerFunctionEnum.Clone Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Clone
helpviewer_keywords:
- ICorProfilerFunctionEnum::Clone method [.NET Framework profiling]
- Clone method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0c3d4835-e111-4e82-af6d-53f140b8f2c9
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 449292d8bacd6bb965119da81671c739f12dc3a3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerfunctionenumclone-method"></a><span data-ttu-id="7a7e7-102">Metodo ICorProfilerFunctionEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="7a7e7-102">ICorProfilerFunctionEnum::Clone Method</span></span>
<span data-ttu-id="7a7e7-103">Ottiene un puntatore a interfaccia a una copia di questo [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="7a7e7-103">Gets an interface pointer to a copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a7e7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7a7e7-104">Syntax</span></span>  
  
```  
HRESULT Clone([out] ICorProfilerFunctionEnum **ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7a7e7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7a7e7-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="7a7e7-106">[out] Un puntatore al puntatore all'interfaccia, che, a sua volta, fa riferimento per la copia di questa [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="7a7e7-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span> <span data-ttu-id="7a7e7-107">La copia dell'enumeratore mantiene il proprio stato di enumerazione separatamente da questo enumeratore.</span><span class="sxs-lookup"><span data-stu-id="7a7e7-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="7a7e7-108">Tuttavia, posizione iniziale del cursore della copia è quella della posizione corrente del cursore dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="7a7e7-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a7e7-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7a7e7-109">Requirements</span></span>  
 <span data-ttu-id="7a7e7-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a7e7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a7e7-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7a7e7-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7a7e7-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a7e7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a7e7-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a7e7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a7e7-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a7e7-114">See Also</span></span>  
 [<span data-ttu-id="7a7e7-115">Interfaccia ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="7a7e7-115">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 [<span data-ttu-id="7a7e7-116">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="7a7e7-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)

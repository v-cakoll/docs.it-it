---
title: Metodo ICorProfilerFunctionEnum::Clone
ms.date: 03/30/2017
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
ms.openlocfilehash: a212a0499b1091f1c77b52951ecef2cb2cace4df
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447841"
---
# <a name="icorprofilerfunctionenumclone-method"></a><span data-ttu-id="506fa-102">Metodo ICorProfilerFunctionEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="506fa-102">ICorProfilerFunctionEnum::Clone Method</span></span>
<span data-ttu-id="506fa-103">Ottiene un puntatore a interfaccia a una copia di questa interfaccia [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="506fa-103">Gets an interface pointer to a copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="506fa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="506fa-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone([out] ICorProfilerFunctionEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="506fa-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="506fa-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="506fa-106">out Puntatore al puntatore a interfaccia, che, a sua volta, punta alla copia dell'interfaccia [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="506fa-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span> <span data-ttu-id="506fa-107">La copia dell'enumeratore mantiene il proprio stato di enumerazione separatamente da questo enumeratore.</span><span class="sxs-lookup"><span data-stu-id="506fa-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="506fa-108">Tuttavia, la posizione iniziale del cursore della copia corrisponde alla posizione corrente del cursore dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="506fa-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="506fa-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="506fa-109">Requirements</span></span>  
 <span data-ttu-id="506fa-110">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="506fa-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="506fa-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="506fa-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="506fa-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="506fa-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="506fa-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="506fa-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="506fa-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="506fa-114">See also</span></span>

- [<span data-ttu-id="506fa-115">Interfaccia ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="506fa-115">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="506fa-116">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="506fa-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)

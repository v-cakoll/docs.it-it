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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b6c1efe2a7d831f26556dbf501176f02588f2e0d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780332"
---
# <a name="icorprofilerfunctionenumclone-method"></a><span data-ttu-id="aa213-102">Metodo ICorProfilerFunctionEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="aa213-102">ICorProfilerFunctionEnum::Clone Method</span></span>
<span data-ttu-id="aa213-103">Ottiene un puntatore a interfaccia a una copia di questo [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="aa213-103">Gets an interface pointer to a copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa213-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aa213-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone([out] ICorProfilerFunctionEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa213-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="aa213-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="aa213-106">[out] Un puntatore al puntatore all'interfaccia, che, a sua volta, fa riferimento alla copia di questo [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="aa213-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span> <span data-ttu-id="aa213-107">La copia dell'enumeratore mantiene il proprio stato di enumerazione separatamente da questo enumeratore.</span><span class="sxs-lookup"><span data-stu-id="aa213-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="aa213-108">Tuttavia, posizione del cursore iniziale della copia sono lo stesso come posizione corrente del cursore dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="aa213-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa213-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="aa213-109">Requirements</span></span>  
 <span data-ttu-id="aa213-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa213-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa213-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="aa213-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="aa213-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa213-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa213-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa213-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa213-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa213-114">See also</span></span>

- [<span data-ttu-id="aa213-115">Interfaccia ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="aa213-115">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="aa213-116">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="aa213-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)

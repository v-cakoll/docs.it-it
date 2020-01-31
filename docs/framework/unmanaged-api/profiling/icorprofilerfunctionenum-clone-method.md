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
ms.openlocfilehash: 2faa7185202b46e77e501d69bb471391a7c6eb68
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864622"
---
# <a name="icorprofilerfunctionenumclone-method"></a><span data-ttu-id="a901b-102">Metodo ICorProfilerFunctionEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="a901b-102">ICorProfilerFunctionEnum::Clone Method</span></span>
<span data-ttu-id="a901b-103">Ottiene un puntatore a interfaccia a una copia di questa interfaccia [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="a901b-103">Gets an interface pointer to a copy of this [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a901b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a901b-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone([out] ICorProfilerFunctionEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a901b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a901b-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="a901b-106">out Puntatore al puntatore a interfaccia, che, a sua volta, punta alla copia dell'interfaccia [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="a901b-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) interface.</span></span> <span data-ttu-id="a901b-107">La copia dell'enumeratore mantiene il proprio stato di enumerazione separatamente da questo enumeratore.</span><span class="sxs-lookup"><span data-stu-id="a901b-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="a901b-108">Tuttavia, la posizione iniziale del cursore della copia corrisponde alla posizione corrente del cursore dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="a901b-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a901b-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="a901b-109">Requirements</span></span>  
 <span data-ttu-id="a901b-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a901b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a901b-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a901b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a901b-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a901b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a901b-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a901b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a901b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a901b-114">See also</span></span>

- [<span data-ttu-id="a901b-115">Interfaccia ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="a901b-115">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="a901b-116">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="a901b-116">Profiling Interfaces</span></span>](profiling-interfaces.md)

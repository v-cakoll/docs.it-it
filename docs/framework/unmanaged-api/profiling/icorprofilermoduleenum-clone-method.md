---
title: Metodo ICorProfilerModuleEnum::Clone
ms.date: 03/30/2017
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
ms.openlocfilehash: a6b36883ec0914426b4f4c937390c1622faead25
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868291"
---
# <a name="icorprofilermoduleenumclone-method"></a><span data-ttu-id="c57f7-102">Metodo ICorProfilerModuleEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="c57f7-102">ICorProfilerModuleEnum::Clone Method</span></span>
<span data-ttu-id="c57f7-103">Ottiene un puntatore a interfaccia a una copia di questa interfaccia [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="c57f7-103">Gets an interface pointer to a copy of this [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c57f7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c57f7-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone([out] ICorProfilerObjectEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c57f7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c57f7-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="c57f7-106">out Puntatore al puntatore a interfaccia che a sua volta punta alla copia dell'interfaccia [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="c57f7-106">[out] A pointer to the interface pointer that in turn points to the copy of this [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) interface.</span></span> <span data-ttu-id="c57f7-107">La copia dell'enumeratore mantiene il proprio stato di enumerazione separatamente da questo enumeratore.</span><span class="sxs-lookup"><span data-stu-id="c57f7-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="c57f7-108">Tuttavia, la posizione iniziale del cursore della copia corrisponde alla posizione corrente del cursore dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="c57f7-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c57f7-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="c57f7-109">Requirements</span></span>  
 <span data-ttu-id="c57f7-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c57f7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c57f7-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c57f7-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c57f7-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c57f7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c57f7-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c57f7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c57f7-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c57f7-114">See also</span></span>

- [<span data-ttu-id="c57f7-115">Interfaccia ICorProfilerModuleEnum</span><span class="sxs-lookup"><span data-stu-id="c57f7-115">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="c57f7-116">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="c57f7-116">Profiling Interfaces</span></span>](profiling-interfaces.md)

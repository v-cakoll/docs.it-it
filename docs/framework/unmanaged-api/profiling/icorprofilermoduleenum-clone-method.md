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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9053505f7356f4618993ead911f730909f53f383
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049414"
---
# <a name="icorprofilermoduleenumclone-method"></a><span data-ttu-id="a76f1-102">Metodo ICorProfilerModuleEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="a76f1-102">ICorProfilerModuleEnum::Clone Method</span></span>
<span data-ttu-id="a76f1-103">Ottiene un puntatore a interfaccia a una copia di questo [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a76f1-103">Gets an interface pointer to a copy of this [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a76f1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a76f1-104">Syntax</span></span>  
  
```  
HRESULT Clone([out] ICorProfilerObjectEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a76f1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a76f1-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="a76f1-106">[out] Un puntatore a puntatore a interfaccia che a sua volta punta alla copia di questo [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a76f1-106">[out] A pointer to the interface pointer that in turn points to the copy of this [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span> <span data-ttu-id="a76f1-107">La copia dell'enumeratore mantiene il proprio stato di enumerazione separatamente da questo enumeratore.</span><span class="sxs-lookup"><span data-stu-id="a76f1-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="a76f1-108">Tuttavia, posizione del cursore iniziale della copia sono lo stesso come posizione corrente del cursore dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="a76f1-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a76f1-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a76f1-109">Requirements</span></span>  
 <span data-ttu-id="a76f1-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a76f1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a76f1-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a76f1-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a76f1-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a76f1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a76f1-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a76f1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a76f1-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a76f1-114">See also</span></span>

- [<span data-ttu-id="a76f1-115">Interfaccia ICorProfilerModuleEnum</span><span class="sxs-lookup"><span data-stu-id="a76f1-115">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="a76f1-116">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="a76f1-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)

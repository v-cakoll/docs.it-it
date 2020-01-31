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
ms.openlocfilehash: 626ecddae8ba91d1830d98210208f9fbee36f073
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868587"
---
# <a name="icorprofilerinfo3enummodules-method"></a><span data-ttu-id="c7a7e-102">Metodo ICorProfilerInfo3::EnumModules</span><span class="sxs-lookup"><span data-stu-id="c7a7e-102">ICorProfilerInfo3::EnumModules Method</span></span>
<span data-ttu-id="c7a7e-103">Restituisce un enumeratore che fornisce i metodi per scorrere in sequenza una raccolta di moduli gestiti caricati nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c7a7e-103">Returns an enumerator that provides methods to sequentially iterate through a collection of managed modules that are loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7a7e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c7a7e-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModules([out] ICorProfilerModuleEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7a7e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c7a7e-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="c7a7e-106">out Puntatore a un'interfaccia [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="c7a7e-106">[out] A pointer to an [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7a7e-107">Note</span><span class="sxs-lookup"><span data-stu-id="c7a7e-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7a7e-108">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="c7a7e-108">Requirements</span></span>  
 <span data-ttu-id="c7a7e-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7a7e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7a7e-110">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c7a7e-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c7a7e-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7a7e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7a7e-112">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7a7e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7a7e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7a7e-113">See also</span></span>

- [<span data-ttu-id="c7a7e-114">Interfaccia ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="c7a7e-114">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="c7a7e-115">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="c7a7e-115">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="c7a7e-116">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="c7a7e-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="c7a7e-117">Profilatura</span><span class="sxs-lookup"><span data-stu-id="c7a7e-117">Profiling</span></span>](index.md)

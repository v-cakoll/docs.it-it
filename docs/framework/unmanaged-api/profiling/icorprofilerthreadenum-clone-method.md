---
title: Metodo ICorProfilerThreadEnum::Clone
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Clone
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Clone method [.NET Framework profiling]
ms.assetid: 5a278bc9-88e2-4c69-b035-9d550dd77081
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 022d0d9c86e4b3b9924b8a486166d8ce3b71e42c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781186"
---
# <a name="icorprofilerthreadenumclone-method"></a><span data-ttu-id="ea65a-102">Metodo ICorProfilerThreadEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="ea65a-102">ICorProfilerThreadEnum::Clone Method</span></span>
<span data-ttu-id="ea65a-103">Ottiene un puntatore a interfaccia a una copia di questo [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="ea65a-103">Gets an interface pointer to a copy of this [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea65a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ea65a-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (    [out] ICorProfilerThreadEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea65a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ea65a-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="ea65a-106">[out] Un puntatore al puntatore all'interfaccia, che, a sua volta, fa riferimento alla copia di questo [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="ea65a-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span> <span data-ttu-id="ea65a-107">La copia dell'enumeratore mantiene il proprio stato di enumerazione separatamente da questo enumeratore.</span><span class="sxs-lookup"><span data-stu-id="ea65a-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="ea65a-108">Tuttavia, la posizione del cursore iniziale della copia è quello utilizzato per questa posizione corrente del cursore dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="ea65a-108">However, the initial cursor position of the copy is the same as this current cursor position of the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea65a-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ea65a-109">Requirements</span></span>  
 <span data-ttu-id="ea65a-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea65a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea65a-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ea65a-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ea65a-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea65a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea65a-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea65a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea65a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea65a-114">See also</span></span>

- [<span data-ttu-id="ea65a-115">ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="ea65a-115">ICorProfilerThreadEnum</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="ea65a-116">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="ea65a-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)

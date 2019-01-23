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
ms.openlocfilehash: 5b9d3224370dac0f8a52affef9201e5cbec43de0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547436"
---
# <a name="icorprofilerthreadenumclone-method"></a><span data-ttu-id="b5971-102">Metodo ICorProfilerThreadEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="b5971-102">ICorProfilerThreadEnum::Clone Method</span></span>
<span data-ttu-id="b5971-103">Ottiene un puntatore a interfaccia a una copia di questo [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="b5971-103">Gets an interface pointer to a copy of this [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5971-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b5971-104">Syntax</span></span>  
  
```  
HRESULT Clone (    [out] ICorProfilerThreadEnum **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b5971-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b5971-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="b5971-106">[out] Un puntatore al puntatore all'interfaccia, che, a sua volta, fa riferimento alla copia di questo [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="b5971-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span> <span data-ttu-id="b5971-107">La copia dell'enumeratore mantiene il proprio stato di enumerazione separatamente da questo enumeratore.</span><span class="sxs-lookup"><span data-stu-id="b5971-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="b5971-108">Tuttavia, la posizione del cursore iniziale della copia è quello utilizzato per questa posizione corrente del cursore dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="b5971-108">However, the initial cursor position of the copy is the same as this current cursor position of the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5971-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b5971-109">Requirements</span></span>  
 <span data-ttu-id="b5971-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5971-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5971-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b5971-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b5971-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5971-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5971-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5971-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5971-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5971-114">See also</span></span>
- [<span data-ttu-id="b5971-115">ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="b5971-115">ICorProfilerThreadEnum</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="b5971-116">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="b5971-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)

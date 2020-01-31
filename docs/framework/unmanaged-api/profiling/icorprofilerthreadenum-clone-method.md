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
ms.openlocfilehash: 9048d314404859a4264621a5da91c43c525027f9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868200"
---
# <a name="icorprofilerthreadenumclone-method"></a><span data-ttu-id="181d9-102">Metodo ICorProfilerThreadEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="181d9-102">ICorProfilerThreadEnum::Clone Method</span></span>
<span data-ttu-id="181d9-103">Ottiene un puntatore a interfaccia a una copia di questa interfaccia [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="181d9-103">Gets an interface pointer to a copy of this [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="181d9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="181d9-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (    [out] ICorProfilerThreadEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="181d9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="181d9-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="181d9-106">out Puntatore al puntatore a interfaccia, che, a sua volta, punta alla copia dell'interfaccia [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="181d9-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span> <span data-ttu-id="181d9-107">La copia dell'enumeratore mantiene il proprio stato di enumerazione separatamente da questo enumeratore.</span><span class="sxs-lookup"><span data-stu-id="181d9-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="181d9-108">Tuttavia, la posizione iniziale del cursore della copia corrisponde alla posizione corrente del cursore dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="181d9-108">However, the initial cursor position of the copy is the same as this current cursor position of the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="181d9-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="181d9-109">Requirements</span></span>  
 <span data-ttu-id="181d9-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="181d9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="181d9-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="181d9-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="181d9-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="181d9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="181d9-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="181d9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="181d9-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="181d9-114">See also</span></span>

- [<span data-ttu-id="181d9-115">ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="181d9-115">ICorProfilerThreadEnum</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="181d9-116">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="181d9-116">Profiling Interfaces</span></span>](profiling-interfaces.md)

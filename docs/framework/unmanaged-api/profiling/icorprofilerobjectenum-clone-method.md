---
title: Metodo ICorProfilerObjectEnum::Clone
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Clone
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerObjectEnum interface [.NET Framework profiling]
- ICorProfilerObjectEnum::Clone method [.NET Framework profiling]
ms.assetid: b0b2facd-5991-4f4c-932d-c4937f45cef9
topic_type:
- apiref
ms.openlocfilehash: a2a54c32c0713b4b69d8f2a0272687cbe9420610
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84494774"
---
# <a name="icorprofilerobjectenumclone-method"></a><span data-ttu-id="be3bd-102">Metodo ICorProfilerObjectEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="be3bd-102">ICorProfilerObjectEnum::Clone Method</span></span>
<span data-ttu-id="be3bd-103">Ottiene un puntatore a interfaccia a una copia di questa interfaccia [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="be3bd-103">Gets an interface pointer to a copy of this [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be3bd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="be3bd-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorProfilerObjectEnum   **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be3bd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="be3bd-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="be3bd-106">out Puntatore al puntatore a interfaccia che a sua volta punta alla copia di questa `ICorProfilerObjectEnum` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="be3bd-106">[out] A pointer to the interface pointer that in turn points to the copy of this `ICorProfilerObjectEnum` interface.</span></span> <span data-ttu-id="be3bd-107">La copia gestisce il proprio stato di enumerazione separatamente da questa.</span><span class="sxs-lookup"><span data-stu-id="be3bd-107">The copy maintains its own enumeration state separately from this one.</span></span> <span data-ttu-id="be3bd-108">Tuttavia, la posizione iniziale del cursore della copia sarà uguale alla posizione corrente del cursore dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="be3bd-108">However, the copy's initial cursor position will be the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be3bd-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="be3bd-109">Requirements</span></span>  
 <span data-ttu-id="be3bd-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be3bd-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be3bd-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="be3bd-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="be3bd-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be3bd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be3bd-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be3bd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be3bd-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be3bd-114">See also</span></span>

- [<span data-ttu-id="be3bd-115">Interfaccia ICorProfilerObjectEnum</span><span class="sxs-lookup"><span data-stu-id="be3bd-115">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)

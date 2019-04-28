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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 14e8086532eff5dba6883575cc2daf447a32343a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597661"
---
# <a name="icorprofilerobjectenumclone-method"></a><span data-ttu-id="716c3-102">Metodo ICorProfilerObjectEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="716c3-102">ICorProfilerObjectEnum::Clone Method</span></span>
<span data-ttu-id="716c3-103">Ottiene un puntatore a interfaccia a una copia di questo [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="716c3-103">Gets an interface pointer to a copy of this [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="716c3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="716c3-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorProfilerObjectEnum   **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="716c3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="716c3-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="716c3-106">[out] Un puntatore a puntatore a interfaccia che a sua volta punta alla copia di questo `ICorProfilerObjectEnum` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="716c3-106">[out] A pointer to the interface pointer that in turn points to the copy of this `ICorProfilerObjectEnum` interface.</span></span> <span data-ttu-id="716c3-107">La copia mantiene il proprio stato di enumerazione separatamente da questo.</span><span class="sxs-lookup"><span data-stu-id="716c3-107">The copy maintains its own enumeration state separately from this one.</span></span> <span data-ttu-id="716c3-108">Tuttavia, posizione del cursore iniziale della copia sarà lo stesso come posizione corrente del cursore dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="716c3-108">However, the copy's initial cursor position will be the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="716c3-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="716c3-109">Requirements</span></span>  
 <span data-ttu-id="716c3-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="716c3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="716c3-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="716c3-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="716c3-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="716c3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="716c3-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="716c3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="716c3-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="716c3-114">See also</span></span>

- [<span data-ttu-id="716c3-115">Interfaccia ICorProfilerObjectEnum</span><span class="sxs-lookup"><span data-stu-id="716c3-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)

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
ms.openlocfilehash: 1013913b62c77714d3cc24eace83272834eecce7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706264"
---
# <a name="icorprofilerobjectenumclone-method"></a><span data-ttu-id="24b05-102">Metodo ICorProfilerObjectEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="24b05-102">ICorProfilerObjectEnum::Clone Method</span></span>
<span data-ttu-id="24b05-103">Ottiene un puntatore a interfaccia a una copia di questo [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="24b05-103">Gets an interface pointer to a copy of this [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24b05-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="24b05-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorProfilerObjectEnum   **ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="24b05-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="24b05-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="24b05-106">[out] Un puntatore a puntatore a interfaccia che a sua volta punta alla copia di questo `ICorProfilerObjectEnum` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="24b05-106">[out] A pointer to the interface pointer that in turn points to the copy of this `ICorProfilerObjectEnum` interface.</span></span> <span data-ttu-id="24b05-107">La copia mantiene il proprio stato di enumerazione separatamente da questo.</span><span class="sxs-lookup"><span data-stu-id="24b05-107">The copy maintains its own enumeration state separately from this one.</span></span> <span data-ttu-id="24b05-108">Tuttavia, posizione del cursore iniziale della copia sarà lo stesso come posizione corrente del cursore dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="24b05-108">However, the copy's initial cursor position will be the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24b05-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="24b05-109">Requirements</span></span>  
 <span data-ttu-id="24b05-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24b05-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24b05-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="24b05-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="24b05-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24b05-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24b05-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24b05-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24b05-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24b05-114">See also</span></span>
- [<span data-ttu-id="24b05-115">Interfaccia ICorProfilerObjectEnum</span><span class="sxs-lookup"><span data-stu-id="24b05-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)

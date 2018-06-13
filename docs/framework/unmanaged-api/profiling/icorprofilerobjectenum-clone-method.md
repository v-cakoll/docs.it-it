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
ms.openlocfilehash: 7e8a623107e5e03ca36137c253c9bdf0a722d385
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456037"
---
# <a name="icorprofilerobjectenumclone-method"></a><span data-ttu-id="3d6ec-102">Metodo ICorProfilerObjectEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="3d6ec-102">ICorProfilerObjectEnum::Clone Method</span></span>
<span data-ttu-id="3d6ec-103">Ottiene un puntatore a interfaccia a una copia di questo [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="3d6ec-103">Gets an interface pointer to a copy of this [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d6ec-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3d6ec-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorProfilerObjectEnum   **ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3d6ec-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3d6ec-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="3d6ec-106">[out] Un puntatore a puntatore a interfaccia che a sua volta punta alla copia di questo `ICorProfilerObjectEnum` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="3d6ec-106">[out] A pointer to the interface pointer that in turn points to the copy of this `ICorProfilerObjectEnum` interface.</span></span> <span data-ttu-id="3d6ec-107">La copia mantiene il proprio stato di enumerazione separatamente da esso.</span><span class="sxs-lookup"><span data-stu-id="3d6ec-107">The copy maintains its own enumeration state separately from this one.</span></span> <span data-ttu-id="3d6ec-108">Tuttavia, posizione iniziale del cursore della copia sarà quella della posizione corrente del cursore dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="3d6ec-108">However, the copy's initial cursor position will be the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d6ec-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3d6ec-109">Requirements</span></span>  
 <span data-ttu-id="3d6ec-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d6ec-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d6ec-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3d6ec-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3d6ec-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="3d6ec-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d6ec-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d6ec-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d6ec-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d6ec-114">See Also</span></span>  
 [<span data-ttu-id="3d6ec-115">Interfaccia ICorProfilerObjectEnum</span><span class="sxs-lookup"><span data-stu-id="3d6ec-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)

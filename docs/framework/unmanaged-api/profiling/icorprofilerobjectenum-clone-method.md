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
ms.openlocfilehash: 8153dbd27e168e3a5bd8e5aeada955a0382aaf75
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868252"
---
# <a name="icorprofilerobjectenumclone-method"></a><span data-ttu-id="31041-102">Metodo ICorProfilerObjectEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="31041-102">ICorProfilerObjectEnum::Clone Method</span></span>
<span data-ttu-id="31041-103">Ottiene un puntatore a interfaccia a una copia di questa interfaccia [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="31041-103">Gets an interface pointer to a copy of this [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31041-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="31041-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorProfilerObjectEnum   **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31041-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="31041-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="31041-106">out Puntatore al puntatore a interfaccia che a sua volta punta alla copia di questa interfaccia `ICorProfilerObjectEnum`.</span><span class="sxs-lookup"><span data-stu-id="31041-106">[out] A pointer to the interface pointer that in turn points to the copy of this `ICorProfilerObjectEnum` interface.</span></span> <span data-ttu-id="31041-107">La copia gestisce il proprio stato di enumerazione separatamente da questa.</span><span class="sxs-lookup"><span data-stu-id="31041-107">The copy maintains its own enumeration state separately from this one.</span></span> <span data-ttu-id="31041-108">Tuttavia, la posizione iniziale del cursore della copia sarà uguale alla posizione corrente del cursore dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="31041-108">However, the copy's initial cursor position will be the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31041-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="31041-109">Requirements</span></span>  
 <span data-ttu-id="31041-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31041-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31041-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="31041-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="31041-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31041-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31041-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31041-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31041-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31041-114">See also</span></span>

- [<span data-ttu-id="31041-115">Interfaccia ICorProfilerObjectEnum</span><span class="sxs-lookup"><span data-stu-id="31041-115">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)

---
title: Metodo ICorProfilerInfo2::EnumModuleFrozenObjects
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.EnumModuleFrozenObjects
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::EnumModuleFrozenObjects
helpviewer_keywords:
- EnumModuleFrozenObjects method [.NET Framework profiling]
- ICorProfilerInfo2::EnumModuleFrozenObjects method [.NET Framework profiling]
ms.assetid: 920b6483-7064-4d64-8613-fcc38ccf9b1e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e9c6d6c77f9609ba1a0762a744b28a93f068b862
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54513321"
---
# <a name="icorprofilerinfo2enummodulefrozenobjects-method"></a><span data-ttu-id="36a90-102">Metodo ICorProfilerInfo2::EnumModuleFrozenObjects</span><span class="sxs-lookup"><span data-stu-id="36a90-102">ICorProfilerInfo2::EnumModuleFrozenObjects Method</span></span>
<span data-ttu-id="36a90-103">Ottiene un enumeratore che consente di scorrere gli oggetti bloccati nel modulo specificato. Questo metodo è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="36a90-103">Gets an enumerator that allows iteration over the frozen objects in the specified module.This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36a90-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="36a90-104">Syntax</span></span>  
  
```  
HRESULT EnumModuleFrozenObjects(  
    [in] ModuleID moduleID,  
    [out] ICorProfilerObjectEnum** ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="36a90-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="36a90-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="36a90-106">[in] L'ID del modulo che contiene gli oggetti bloccati da enumerare.</span><span class="sxs-lookup"><span data-stu-id="36a90-106">[in] The ID of the module that contains the frozen objects to be enumerated.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="36a90-107">[out] Un puntatore all'indirizzo di un [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interfaccia, che enumera gli oggetti bloccati.</span><span class="sxs-lookup"><span data-stu-id="36a90-107">[out] A pointer to the address of an [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface, which enumerates the frozen objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36a90-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="36a90-108">Requirements</span></span>  
 <span data-ttu-id="36a90-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36a90-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36a90-110">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="36a90-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="36a90-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36a90-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36a90-112">**Versioni di .NET framework:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0</span><span class="sxs-lookup"><span data-stu-id="36a90-112">**.NET Framework Versions:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36a90-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36a90-113">See also</span></span>
- [<span data-ttu-id="36a90-114">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="36a90-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="36a90-115">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="36a90-115">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)

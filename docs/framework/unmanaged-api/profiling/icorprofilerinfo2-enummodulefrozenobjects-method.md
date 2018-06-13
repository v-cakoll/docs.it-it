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
ms.openlocfilehash: 77b07dae5b53db58b3628f677be1714e66ac18ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455257"
---
# <a name="icorprofilerinfo2enummodulefrozenobjects-method"></a><span data-ttu-id="90099-102">Metodo ICorProfilerInfo2::EnumModuleFrozenObjects</span><span class="sxs-lookup"><span data-stu-id="90099-102">ICorProfilerInfo2::EnumModuleFrozenObjects Method</span></span>
<span data-ttu-id="90099-103">Ottiene un enumeratore che consente di scorrere gli oggetti bloccati nel modulo specificato. Questo metodo è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="90099-103">Gets an enumerator that allows iteration over the frozen objects in the specified module.This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90099-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="90099-104">Syntax</span></span>  
  
```  
HRESULT EnumModuleFrozenObjects(  
    [in] ModuleID moduleID,  
    [out] ICorProfilerObjectEnum** ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="90099-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="90099-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="90099-106">[in] L'ID del modulo che contiene gli oggetti bloccati da enumerare.</span><span class="sxs-lookup"><span data-stu-id="90099-106">[in] The ID of the module that contains the frozen objects to be enumerated.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="90099-107">[out] Un puntatore all'indirizzo di un [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interfaccia che enumera gli oggetti bloccati.</span><span class="sxs-lookup"><span data-stu-id="90099-107">[out] A pointer to the address of an [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface, which enumerates the frozen objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90099-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="90099-108">Requirements</span></span>  
 <span data-ttu-id="90099-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90099-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90099-110">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="90099-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="90099-111">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="90099-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90099-112">**Versioni di .NET framework:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0</span><span class="sxs-lookup"><span data-stu-id="90099-112">**.NET Framework Versions:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90099-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90099-113">See Also</span></span>  
 [<span data-ttu-id="90099-114">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="90099-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="90099-115">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="90099-115">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)

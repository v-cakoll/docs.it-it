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
ms.openlocfilehash: 51e0c5b08b8a2ac3b8eaf38cdabd682078ba70c8
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436046"
---
# <a name="icorprofilerinfo2enummodulefrozenobjects-method"></a><span data-ttu-id="0d859-102">Metodo ICorProfilerInfo2::EnumModuleFrozenObjects</span><span class="sxs-lookup"><span data-stu-id="0d859-102">ICorProfilerInfo2::EnumModuleFrozenObjects Method</span></span>
<span data-ttu-id="0d859-103">Ottiene un enumeratore che consente l'iterazione sugli oggetti bloccati nel modulo specificato. Questo metodo è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="0d859-103">Gets an enumerator that allows iteration over the frozen objects in the specified module.This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d859-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0d859-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModuleFrozenObjects(  
    [in] ModuleID moduleID,  
    [out] ICorProfilerObjectEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d859-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0d859-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="0d859-106">in ID del modulo che contiene gli oggetti bloccati da enumerare.</span><span class="sxs-lookup"><span data-stu-id="0d859-106">[in] The ID of the module that contains the frozen objects to be enumerated.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="0d859-107">out Puntatore all'indirizzo di un'interfaccia [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) , che enumera gli oggetti bloccati.</span><span class="sxs-lookup"><span data-stu-id="0d859-107">[out] A pointer to the address of an [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface, which enumerates the frozen objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d859-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0d859-108">Requirements</span></span>  
 <span data-ttu-id="0d859-109">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d859-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d859-110">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0d859-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0d859-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d859-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d859-112">**Versioni .NET Framework:** 3,5, 3,0 sp1, 3,0, 2,0 SP1, 2,0</span><span class="sxs-lookup"><span data-stu-id="0d859-112">**.NET Framework Versions:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d859-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d859-113">See also</span></span>

- [<span data-ttu-id="0d859-114">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="0d859-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="0d859-115">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="0d859-115">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)

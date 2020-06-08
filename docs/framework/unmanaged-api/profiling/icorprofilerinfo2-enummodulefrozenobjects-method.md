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
ms.openlocfilehash: 1fe44f8f84c079e920c8c82fb9d52d1980d3b852
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497205"
---
# <a name="icorprofilerinfo2enummodulefrozenobjects-method"></a><span data-ttu-id="f037d-102">Metodo ICorProfilerInfo2::EnumModuleFrozenObjects</span><span class="sxs-lookup"><span data-stu-id="f037d-102">ICorProfilerInfo2::EnumModuleFrozenObjects Method</span></span>
<span data-ttu-id="f037d-103">Ottiene un enumeratore che consente l'iterazione sugli oggetti bloccati nel modulo specificato. Questo metodo è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f037d-103">Gets an enumerator that allows iteration over the frozen objects in the specified module.This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f037d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f037d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModuleFrozenObjects(  
    [in] ModuleID moduleID,  
    [out] ICorProfilerObjectEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f037d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f037d-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="f037d-106">in ID del modulo che contiene gli oggetti bloccati da enumerare.</span><span class="sxs-lookup"><span data-stu-id="f037d-106">[in] The ID of the module that contains the frozen objects to be enumerated.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="f037d-107">out Puntatore all'indirizzo di un'interfaccia [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) , che enumera gli oggetti bloccati.</span><span class="sxs-lookup"><span data-stu-id="f037d-107">[out] A pointer to the address of an [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) interface, which enumerates the frozen objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f037d-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f037d-108">Requirements</span></span>  
 <span data-ttu-id="f037d-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f037d-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f037d-110">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f037d-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f037d-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f037d-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f037d-112">**Versioni .NET Framework:** 3,5, 3,0 sp1, 3,0, 2,0 SP1, 2,0</span><span class="sxs-lookup"><span data-stu-id="f037d-112">**.NET Framework Versions:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f037d-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f037d-113">See also</span></span>

- [<span data-ttu-id="f037d-114">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="f037d-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="f037d-115">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="f037d-115">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)

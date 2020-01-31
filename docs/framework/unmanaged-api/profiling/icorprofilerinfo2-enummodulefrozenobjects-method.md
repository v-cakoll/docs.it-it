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
ms.openlocfilehash: 27b3037459ac4f995e37515f6e96c28449c80a4f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862945"
---
# <a name="icorprofilerinfo2enummodulefrozenobjects-method"></a><span data-ttu-id="b2080-102">Metodo ICorProfilerInfo2::EnumModuleFrozenObjects</span><span class="sxs-lookup"><span data-stu-id="b2080-102">ICorProfilerInfo2::EnumModuleFrozenObjects Method</span></span>
<span data-ttu-id="b2080-103">Ottiene un enumeratore che consente l'iterazione sugli oggetti bloccati nel modulo specificato. Questo metodo è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="b2080-103">Gets an enumerator that allows iteration over the frozen objects in the specified module.This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2080-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b2080-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModuleFrozenObjects(  
    [in] ModuleID moduleID,  
    [out] ICorProfilerObjectEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2080-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b2080-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="b2080-106">in ID del modulo che contiene gli oggetti bloccati da enumerare.</span><span class="sxs-lookup"><span data-stu-id="b2080-106">[in] The ID of the module that contains the frozen objects to be enumerated.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="b2080-107">out Puntatore all'indirizzo di un'interfaccia [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) , che enumera gli oggetti bloccati.</span><span class="sxs-lookup"><span data-stu-id="b2080-107">[out] A pointer to the address of an [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) interface, which enumerates the frozen objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2080-108">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="b2080-108">Requirements</span></span>  
 <span data-ttu-id="b2080-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2080-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2080-110">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b2080-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b2080-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2080-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2080-112">**Versioni .NET Framework:** 3,5, 3,0 sp1, 3,0, 2,0 SP1, 2,0</span><span class="sxs-lookup"><span data-stu-id="b2080-112">**.NET Framework Versions:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2080-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2080-113">See also</span></span>

- [<span data-ttu-id="b2080-114">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="b2080-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="b2080-115">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="b2080-115">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)

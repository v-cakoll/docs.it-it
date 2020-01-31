---
title: Metodo ICorProfilerInfo::GetFunctionFromToken
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetFunctionFromToken method [.NET Framework profiling]
- GetFunctionFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0eed759f-cce8-405d-88dc-9ee293a38928
topic_type:
- apiref
ms.openlocfilehash: 2b2d619c5940376806e9873a528b4f08886593e9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863556"
---
# <a name="icorprofilerinfogetfunctionfromtoken-method"></a><span data-ttu-id="428d4-102">Metodo ICorProfilerInfo::GetFunctionFromToken</span><span class="sxs-lookup"><span data-stu-id="428d4-102">ICorProfilerInfo::GetFunctionFromToken Method</span></span>
<span data-ttu-id="428d4-103">Ottiene l'ID di una funzione.</span><span class="sxs-lookup"><span data-stu-id="428d4-103">Gets the ID of a function.</span></span> <span data-ttu-id="428d4-104">Questo metodo è obsoleto nella versione .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="428d4-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="428d4-105">Usare invece il metodo [ICorProfilerInfo2:: GetFunctionFromTokenAndTypeArgs](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) .</span><span class="sxs-lookup"><span data-stu-id="428d4-105">Use the [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="428d4-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="428d4-106">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in]  ModuleID   moduleId,  
    [in]  mdToken    token,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="remarks"></a><span data-ttu-id="428d4-107">Note</span><span class="sxs-lookup"><span data-stu-id="428d4-107">Remarks</span></span>  
 <span data-ttu-id="428d4-108">Il metodo `GetFunctionFromToken` non funzionerà per funzioni o funzioni generiche nei tipi generici; è ora obsoleto.</span><span class="sxs-lookup"><span data-stu-id="428d4-108">The `GetFunctionFromToken` method will not work for generic functions or functions in generic types; it is now obsolete.</span></span> <span data-ttu-id="428d4-109">Usare `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` per tutte le funzioni.</span><span class="sxs-lookup"><span data-stu-id="428d4-109">Use `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` for all functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="428d4-110">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="428d4-110">Requirements</span></span>  
 <span data-ttu-id="428d4-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="428d4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="428d4-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="428d4-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="428d4-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="428d4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="428d4-114">**Versioni .NET Framework:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="428d4-114">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="428d4-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="428d4-115">See also</span></span>

- [<span data-ttu-id="428d4-116">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="428d4-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)

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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eb894e3f52d28ce419ddda90f9fc0ac0e8dce022
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461942"
---
# <a name="icorprofilerinfogetfunctionfromtoken-method"></a><span data-ttu-id="ac025-102">Metodo ICorProfilerInfo::GetFunctionFromToken</span><span class="sxs-lookup"><span data-stu-id="ac025-102">ICorProfilerInfo::GetFunctionFromToken Method</span></span>
<span data-ttu-id="ac025-103">Ottiene l'ID di una funzione.</span><span class="sxs-lookup"><span data-stu-id="ac025-103">Gets the ID of a function.</span></span> <span data-ttu-id="ac025-104">Questo metodo è obsoleto in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="ac025-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="ac025-105">Utilizzare il [ICorProfilerInfo2:: GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="ac025-105">Use the [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac025-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ac025-106">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromToken(  
    [in]  ModuleID   moduleId,  
    [in]  mdToken    token,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="remarks"></a><span data-ttu-id="ac025-107">Note</span><span class="sxs-lookup"><span data-stu-id="ac025-107">Remarks</span></span>  
 <span data-ttu-id="ac025-108">Il `GetFunctionFromToken` (metodo) non funzioneranno per le funzioni generiche o in tipi generici; è ora obsoleta.</span><span class="sxs-lookup"><span data-stu-id="ac025-108">The `GetFunctionFromToken` method will not work for generic functions or functions in generic types; it is now obsolete.</span></span> <span data-ttu-id="ac025-109">Utilizzare `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` per tutte le funzioni.</span><span class="sxs-lookup"><span data-stu-id="ac025-109">Use `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` for all functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac025-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ac025-110">Requirements</span></span>  
 <span data-ttu-id="ac025-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac025-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac025-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ac025-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ac025-113">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="ac025-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac025-114">**Versioni di .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="ac025-114">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac025-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac025-115">See Also</span></span>  
 [<span data-ttu-id="ac025-116">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="ac025-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)

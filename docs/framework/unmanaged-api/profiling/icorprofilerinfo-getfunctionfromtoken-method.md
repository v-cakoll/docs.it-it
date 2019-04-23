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
ms.openlocfilehash: 5f4fb2292154a2660a2db3f0b3962fcf2114e385
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59099976"
---
# <a name="icorprofilerinfogetfunctionfromtoken-method"></a><span data-ttu-id="5ccd4-102">Metodo ICorProfilerInfo::GetFunctionFromToken</span><span class="sxs-lookup"><span data-stu-id="5ccd4-102">ICorProfilerInfo::GetFunctionFromToken Method</span></span>
<span data-ttu-id="5ccd4-103">Ottiene l'ID di una funzione.</span><span class="sxs-lookup"><span data-stu-id="5ccd4-103">Gets the ID of a function.</span></span> <span data-ttu-id="5ccd4-104">Questo metodo è obsoleto in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="5ccd4-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="5ccd4-105">Usare la [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="5ccd4-105">Use the [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ccd4-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5ccd4-106">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromToken(  
    [in]  ModuleID   moduleId,  
    [in]  mdToken    token,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="remarks"></a><span data-ttu-id="5ccd4-107">Note</span><span class="sxs-lookup"><span data-stu-id="5ccd4-107">Remarks</span></span>  
 <span data-ttu-id="5ccd4-108">Il `GetFunctionFromToken` (metodo) non funzioneranno per le funzioni in tipi generici o funzioni generiche, è ora obsoleto.</span><span class="sxs-lookup"><span data-stu-id="5ccd4-108">The `GetFunctionFromToken` method will not work for generic functions or functions in generic types; it is now obsolete.</span></span> <span data-ttu-id="5ccd4-109">Usare `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` per tutte le funzioni.</span><span class="sxs-lookup"><span data-stu-id="5ccd4-109">Use `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` for all functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ccd4-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5ccd4-110">Requirements</span></span>  
 <span data-ttu-id="5ccd4-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ccd4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ccd4-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5ccd4-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5ccd4-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ccd4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ccd4-114">**Versioni di .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="5ccd4-114">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ccd4-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ccd4-115">See also</span></span>

- [<span data-ttu-id="5ccd4-116">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="5ccd4-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)

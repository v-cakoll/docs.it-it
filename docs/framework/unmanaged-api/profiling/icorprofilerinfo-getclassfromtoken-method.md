---
title: Metodo ICorProfilerInfo::GetClassFromToken
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetClassFromToken method [.NET Framework profiling]
- GetClassFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0afc1197-2a5b-424f-8b82-9cb59a7e00db
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a74e99e0b669c1b3d8e36d881391f27ef71ae306
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57493544"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a><span data-ttu-id="47394-102">Metodo ICorProfilerInfo::GetClassFromToken</span><span class="sxs-lookup"><span data-stu-id="47394-102">ICorProfilerInfo::GetClassFromToken Method</span></span>
<span data-ttu-id="47394-103">Ottiene l'ID della classe, dato il token di metadati.</span><span class="sxs-lookup"><span data-stu-id="47394-103">Gets the ID of the class, given the metadata token.</span></span> <span data-ttu-id="47394-104">Questo metodo è obsoleto in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="47394-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="47394-105">Uso [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) invece.</span><span class="sxs-lookup"><span data-stu-id="47394-105">Use [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47394-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="47394-106">Syntax</span></span>  
  
```  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47394-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="47394-107">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="47394-108">[in] L'ID del modulo che contiene la classe.</span><span class="sxs-lookup"><span data-stu-id="47394-108">[in] The ID of the module that contains the class.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="47394-109">[in] Un `mdTypeDef` token di metadati che fa riferimento alla classe.</span><span class="sxs-lookup"><span data-stu-id="47394-109">[in] An `mdTypeDef` metadata token that references the class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="47394-110">[out] Un puntatore all'ID di classe.</span><span class="sxs-lookup"><span data-stu-id="47394-110">[out] A pointer to the class ID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47394-111">Note</span><span class="sxs-lookup"><span data-stu-id="47394-111">Remarks</span></span>  
 <span data-ttu-id="47394-112">Questo metodo è obsoleto. Usare invece `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` per tutti i tipi.</span><span class="sxs-lookup"><span data-stu-id="47394-112">This method is obsolete; instead, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` for all types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47394-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="47394-113">Requirements</span></span>  
 <span data-ttu-id="47394-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47394-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47394-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="47394-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="47394-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47394-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47394-117">**Versioni di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="47394-117">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47394-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47394-118">See also</span></span>
- [<span data-ttu-id="47394-119">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="47394-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)

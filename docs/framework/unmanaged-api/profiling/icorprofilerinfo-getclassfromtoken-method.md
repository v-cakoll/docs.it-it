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
ms.openlocfilehash: 12b4b897f9dc51175037d39c0368b6ce59fefefb
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498479"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a><span data-ttu-id="d9157-102">Metodo ICorProfilerInfo::GetClassFromToken</span><span class="sxs-lookup"><span data-stu-id="d9157-102">ICorProfilerInfo::GetClassFromToken Method</span></span>
<span data-ttu-id="d9157-103">Ottiene l'ID della classe, dato il token di metadati.</span><span class="sxs-lookup"><span data-stu-id="d9157-103">Gets the ID of the class, given the metadata token.</span></span> <span data-ttu-id="d9157-104">Questo metodo è obsoleto nella versione .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="d9157-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="d9157-105">Usare invece [ICorProfilerInfo2:: GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d9157-105">Use [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9157-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d9157-106">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9157-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="d9157-107">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="d9157-108">in ID del modulo che contiene la classe.</span><span class="sxs-lookup"><span data-stu-id="d9157-108">[in] The ID of the module that contains the class.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="d9157-109">in `mdTypeDef`Token di metadati che fa riferimento alla classe.</span><span class="sxs-lookup"><span data-stu-id="d9157-109">[in] An `mdTypeDef` metadata token that references the class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="d9157-110">out Puntatore all'ID della classe.</span><span class="sxs-lookup"><span data-stu-id="d9157-110">[out] A pointer to the class ID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9157-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d9157-111">Remarks</span></span>  
 <span data-ttu-id="d9157-112">Questo metodo è obsoleto; usare invece `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` per tutti i tipi.</span><span class="sxs-lookup"><span data-stu-id="d9157-112">This method is obsolete; instead, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` for all types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9157-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d9157-113">Requirements</span></span>  
 <span data-ttu-id="d9157-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9157-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9157-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d9157-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d9157-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9157-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9157-117">**Versioni .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="d9157-117">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9157-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9157-118">See also</span></span>

- [<span data-ttu-id="d9157-119">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="d9157-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)

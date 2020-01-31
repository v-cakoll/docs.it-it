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
ms.openlocfilehash: 841953625235406f013e9f140ad91c7b65680e47
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863953"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a><span data-ttu-id="182ff-102">Metodo ICorProfilerInfo::GetClassFromToken</span><span class="sxs-lookup"><span data-stu-id="182ff-102">ICorProfilerInfo::GetClassFromToken Method</span></span>
<span data-ttu-id="182ff-103">Ottiene l'ID della classe, dato il token di metadati.</span><span class="sxs-lookup"><span data-stu-id="182ff-103">Gets the ID of the class, given the metadata token.</span></span> <span data-ttu-id="182ff-104">Questo metodo è obsoleto nella versione .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="182ff-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="182ff-105">Usare invece [ICorProfilerInfo2:: GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) .</span><span class="sxs-lookup"><span data-stu-id="182ff-105">Use [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="182ff-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="182ff-106">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="182ff-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="182ff-107">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="182ff-108">in ID del modulo che contiene la classe.</span><span class="sxs-lookup"><span data-stu-id="182ff-108">[in] The ID of the module that contains the class.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="182ff-109">in Token di metadati `mdTypeDef` che fa riferimento alla classe.</span><span class="sxs-lookup"><span data-stu-id="182ff-109">[in] An `mdTypeDef` metadata token that references the class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="182ff-110">out Puntatore all'ID della classe.</span><span class="sxs-lookup"><span data-stu-id="182ff-110">[out] A pointer to the class ID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="182ff-111">Note</span><span class="sxs-lookup"><span data-stu-id="182ff-111">Remarks</span></span>  
 <span data-ttu-id="182ff-112">Questo metodo è obsoleto; usare invece `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` per tutti i tipi.</span><span class="sxs-lookup"><span data-stu-id="182ff-112">This method is obsolete; instead, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` for all types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="182ff-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="182ff-113">Requirements</span></span>  
 <span data-ttu-id="182ff-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="182ff-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="182ff-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="182ff-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="182ff-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="182ff-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="182ff-117">**Versioni .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="182ff-117">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="182ff-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="182ff-118">See also</span></span>

- [<span data-ttu-id="182ff-119">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="182ff-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)

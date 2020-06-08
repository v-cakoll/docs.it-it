---
title: Metodo ICorProfilerInfo::GetCodeInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetCodeInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetCodeInfo
helpviewer_keywords:
- GetCodeInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetCodeInfo method [.NET Framework profiling]
ms.assetid: 90140b0f-a926-4a7e-b6fa-23e05f703cce
topic_type:
- apiref
ms.openlocfilehash: eb6efc738b270f8f76d7130a12af4927fb6220ce
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498362"
---
# <a name="icorprofilerinfogetcodeinfo-method"></a><span data-ttu-id="46dde-102">Metodo ICorProfilerInfo::GetCodeInfo</span><span class="sxs-lookup"><span data-stu-id="46dde-102">ICorProfilerInfo::GetCodeInfo Method</span></span>
<span data-ttu-id="46dde-103">Ottiene l'ambito del codice nativo associato all'ID funzione specificato.</span><span class="sxs-lookup"><span data-stu-id="46dde-103">Gets the extent of native code associated with the specified function ID.</span></span>  
  
 <span data-ttu-id="46dde-104">Questo metodo è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="46dde-104">This method is obsolete.</span></span> <span data-ttu-id="46dde-105">Usare invece il metodo [ICorProfilerInfo2:: GetCodeInfo2](icorprofilerinfo2-getcodeinfo2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="46dde-105">Use the [ICorProfilerInfo2::GetCodeInfo2](icorprofilerinfo2-getcodeinfo2-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46dde-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="46dde-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCodeInfo(  
    [in]  FunctionID functionId,  
    [out] LPCBYTE    *pStart,  
    [out] ULONG      *pcSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46dde-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="46dde-107">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="46dde-108">[in] ID della funzione alla quale è associato il codice nativo.</span><span class="sxs-lookup"><span data-stu-id="46dde-108">[in] The ID of the function with which the native code is associated.</span></span>  
  
 `pStart`  
 <span data-ttu-id="46dde-109">[out] Puntatore a una matrice di byte che costituiscono il codice nativo della funzione.</span><span class="sxs-lookup"><span data-stu-id="46dde-109">[out] A pointer to an array of bytes that compose the native code of the function.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="46dde-110">[out] Puntatore a un intero che specifica la dimensione, in byte, del codice nativo.</span><span class="sxs-lookup"><span data-stu-id="46dde-110">[out] A pointer to an integer that specifies the size, in bytes, of the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46dde-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="46dde-111">Remarks</span></span>  
 <span data-ttu-id="46dde-112">Per ottimizzare le prestazioni, il runtime di .NET Framework versione 2.0 divide in più aree il codice nativo precompilato di una funzione.</span><span class="sxs-lookup"><span data-stu-id="46dde-112">To optimize performance, the runtime in the .NET Framework version 2.0 splits the precompiled, native code of a function into multiple regions.</span></span> <span data-ttu-id="46dde-113">Il metodo `GetCodeInfo` pertanto è obsoleto in .NET Framework 2.0 perché non è in grado di gestire l'ambito del codice nativo di una funzione.</span><span class="sxs-lookup"><span data-stu-id="46dde-113">Consequently, the `GetCodeInfo` method is obsolete in the .NET Framework 2.0 because it is unable to handle the extent of a function's native code.</span></span> <span data-ttu-id="46dde-114">I profiler devono invece iniziare a usare il metodo più generico `ICorProfilerInfo2::GetCodeInfo2`.</span><span class="sxs-lookup"><span data-stu-id="46dde-114">Profilers should switch to using the more general `ICorProfilerInfo2::GetCodeInfo2` method instead.</span></span>  
  
 <span data-ttu-id="46dde-115">Questa funzione usa buffer allocati dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="46dde-115">This function uses caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46dde-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="46dde-116">Requirements</span></span>  
 <span data-ttu-id="46dde-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46dde-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46dde-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="46dde-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="46dde-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46dde-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46dde-120">**Versioni .NET Framework:** 1,0</span><span class="sxs-lookup"><span data-stu-id="46dde-120">**.NET Framework Versions:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46dde-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46dde-121">See also</span></span>

- [<span data-ttu-id="46dde-122">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="46dde-122">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="46dde-123">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="46dde-123">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="46dde-124">Profilatura</span><span class="sxs-lookup"><span data-stu-id="46dde-124">Profiling</span></span>](index.md)

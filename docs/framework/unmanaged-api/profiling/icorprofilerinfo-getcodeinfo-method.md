---
title: Metodo ICorProfilerInfo::GetCodeInfo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cd05f1ed64e32c4b451f3e60d856be0e99e302b1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetcodeinfo-method"></a><span data-ttu-id="0fa16-102">Metodo ICorProfilerInfo::GetCodeInfo</span><span class="sxs-lookup"><span data-stu-id="0fa16-102">ICorProfilerInfo::GetCodeInfo Method</span></span>
<span data-ttu-id="0fa16-103">Ottiene l'ambito del codice nativo associato all'ID funzione specificato.</span><span class="sxs-lookup"><span data-stu-id="0fa16-103">Gets the extent of native code associated with the specified function ID.</span></span>  
  
 <span data-ttu-id="0fa16-104">Questo metodo è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="0fa16-104">This method is obsolete.</span></span> <span data-ttu-id="0fa16-105">Utilizzare il [ICorProfilerInfo2:: Getcodeinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="0fa16-105">Use the [ICorProfilerInfo2::GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fa16-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0fa16-106">Syntax</span></span>  
  
```  
HRESULT GetCodeInfo(  
    [in]  FunctionID functionId,  
    [out] LPCBYTE    *pStart,  
    [out] ULONG      *pcSize);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0fa16-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="0fa16-107">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="0fa16-108">[in] ID della funzione alla quale è associato il codice nativo.</span><span class="sxs-lookup"><span data-stu-id="0fa16-108">[in] The ID of the function with which the native code is associated.</span></span>  
  
 `pStart`  
 <span data-ttu-id="0fa16-109">[out] Puntatore a una matrice di byte che costituiscono il codice nativo della funzione.</span><span class="sxs-lookup"><span data-stu-id="0fa16-109">[out] A pointer to an array of bytes that compose the native code of the function.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="0fa16-110">[out] Puntatore a un intero che specifica la dimensione, in byte, del codice nativo.</span><span class="sxs-lookup"><span data-stu-id="0fa16-110">[out] A pointer to an integer that specifies the size, in bytes, of the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0fa16-111">Note</span><span class="sxs-lookup"><span data-stu-id="0fa16-111">Remarks</span></span>  
 <span data-ttu-id="0fa16-112">Per ottimizzare le prestazioni, il runtime di .NET Framework versione 2.0 divide in più aree il codice nativo precompilato di una funzione.</span><span class="sxs-lookup"><span data-stu-id="0fa16-112">To optimize performance, the runtime in the .NET Framework version 2.0 splits the precompiled, native code of a function into multiple regions.</span></span> <span data-ttu-id="0fa16-113">Il metodo `GetCodeInfo` pertanto è obsoleto in .NET Framework 2.0 perché non è in grado di gestire l'ambito del codice nativo di una funzione.</span><span class="sxs-lookup"><span data-stu-id="0fa16-113">Consequently, the `GetCodeInfo` method is obsolete in the .NET Framework 2.0 because it is unable to handle the extent of a function's native code.</span></span> <span data-ttu-id="0fa16-114">I profiler devono invece iniziare a usare il metodo più generico `ICorProfilerInfo2::GetCodeInfo2`.</span><span class="sxs-lookup"><span data-stu-id="0fa16-114">Profilers should switch to using the more general `ICorProfilerInfo2::GetCodeInfo2` method instead.</span></span>  
  
 <span data-ttu-id="0fa16-115">Questa funzione usa buffer allocati dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="0fa16-115">This function uses caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fa16-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0fa16-116">Requirements</span></span>  
 <span data-ttu-id="0fa16-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fa16-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fa16-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0fa16-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0fa16-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0fa16-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0fa16-120">**Versioni di .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="0fa16-120">**.NET Framework Versions:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fa16-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0fa16-121">See Also</span></span>  
 [<span data-ttu-id="0fa16-122">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="0fa16-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="0fa16-123">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="0fa16-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="0fa16-124">Profilatura</span><span class="sxs-lookup"><span data-stu-id="0fa16-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)

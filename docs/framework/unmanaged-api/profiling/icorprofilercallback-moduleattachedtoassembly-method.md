---
title: Metodo ICorProfilerCallback::ModuleAttachedToAssembly
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleAttachedToAssembly
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly
helpviewer_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly method [.NET Framework profiling]
- ModuleAttachedToAssembly method [.NET Framework profiling]
ms.assetid: b595798a-5d40-4cac-ab4f-911c61d2c5d2
topic_type:
- apiref
ms.openlocfilehash: cb342b1c328daca5b3cfc0440e6f276ae54e3ed8
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866182"
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a><span data-ttu-id="d0ed4-102">Metodo ICorProfilerCallback::ModuleAttachedToAssembly</span><span class="sxs-lookup"><span data-stu-id="d0ed4-102">ICorProfilerCallback::ModuleAttachedToAssembly Method</span></span>
<span data-ttu-id="d0ed4-103">Notifica al profiler che un modulo viene collegato al relativo assembly padre.</span><span class="sxs-lookup"><span data-stu-id="d0ed4-103">Notifies the profiler that a module is being attached to its parent assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0ed4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d0ed4-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleAttachedToAssembly(  
    [in] ModuleID   moduleId,  
    [in] AssemblyID AssemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0ed4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d0ed4-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="d0ed4-106">in ID del modulo che viene collegato.</span><span class="sxs-lookup"><span data-stu-id="d0ed4-106">[in] The ID of the module that is being attached.</span></span>  
  
 `AssemblyId`  
 <span data-ttu-id="d0ed4-107">in ID dell'assembly padre a cui è collegato il modulo.</span><span class="sxs-lookup"><span data-stu-id="d0ed4-107">[in] The ID of the parent assembly to which the module is attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0ed4-108">Note</span><span class="sxs-lookup"><span data-stu-id="d0ed4-108">Remarks</span></span>  
 <span data-ttu-id="d0ed4-109">Un modulo può essere caricato tramite una tabella di indirizzi di importazione (IAT), tramite una chiamata a `LoadLibrary`o tramite un riferimento ai metadati.</span><span class="sxs-lookup"><span data-stu-id="d0ed4-109">A module can be loaded through an import address table (IAT), through a call to `LoadLibrary`, or through a metadata reference.</span></span> <span data-ttu-id="d0ed4-110">Di conseguenza, il caricatore di Common Language Runtime (CLR) ha più percorsi di codice per determinare l'assembly in cui risiede un modulo.</span><span class="sxs-lookup"><span data-stu-id="d0ed4-110">As a result, the common language runtime (CLR) loader has multiple code paths for determining the assembly in which a module lives.</span></span> <span data-ttu-id="d0ed4-111">Di conseguenza, è possibile che dopo la chiamata a [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) il modulo non conosca l'assembly in cui si trova e non sia possibile ottenere l'ID dell'assembly padre.</span><span class="sxs-lookup"><span data-stu-id="d0ed4-111">Therefore, it is possible that after [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) is called, the module does not know what assembly it is in and getting the parent assembly ID is not possible.</span></span> <span data-ttu-id="d0ed4-112">Il metodo `ModuleAttachedToAssembly` viene chiamato quando il modulo viene collegato al relativo assembly padre ed è possibile ottenere il relativo ID assembly padre.</span><span class="sxs-lookup"><span data-stu-id="d0ed4-112">The `ModuleAttachedToAssembly` method is called when the module is attached to its parent assembly and its parent assembly ID can be obtained.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0ed4-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="d0ed4-113">Requirements</span></span>  
 <span data-ttu-id="d0ed4-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0ed4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0ed4-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d0ed4-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d0ed4-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0ed4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0ed4-117">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0ed4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0ed4-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0ed4-118">See also</span></span>

- [<span data-ttu-id="d0ed4-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="d0ed4-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)

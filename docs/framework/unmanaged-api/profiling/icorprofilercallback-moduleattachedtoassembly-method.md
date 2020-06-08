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
ms.openlocfilehash: 4f494919d11e0f979cf1964c08106fbb9b9ed20b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503393"
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a><span data-ttu-id="3625a-102">Metodo ICorProfilerCallback::ModuleAttachedToAssembly</span><span class="sxs-lookup"><span data-stu-id="3625a-102">ICorProfilerCallback::ModuleAttachedToAssembly Method</span></span>
<span data-ttu-id="3625a-103">Notifica al profiler che un modulo viene collegato al relativo assembly padre.</span><span class="sxs-lookup"><span data-stu-id="3625a-103">Notifies the profiler that a module is being attached to its parent assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3625a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3625a-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleAttachedToAssembly(  
    [in] ModuleID   moduleId,  
    [in] AssemblyID AssemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3625a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3625a-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="3625a-106">in ID del modulo che viene collegato.</span><span class="sxs-lookup"><span data-stu-id="3625a-106">[in] The ID of the module that is being attached.</span></span>  
  
 `AssemblyId`  
 <span data-ttu-id="3625a-107">in ID dell'assembly padre a cui è collegato il modulo.</span><span class="sxs-lookup"><span data-stu-id="3625a-107">[in] The ID of the parent assembly to which the module is attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3625a-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3625a-108">Remarks</span></span>  
 <span data-ttu-id="3625a-109">Un modulo può essere caricato tramite una tabella di indirizzi di importazione (IAT), tramite una chiamata a `LoadLibrary` o tramite un riferimento ai metadati.</span><span class="sxs-lookup"><span data-stu-id="3625a-109">A module can be loaded through an import address table (IAT), through a call to `LoadLibrary`, or through a metadata reference.</span></span> <span data-ttu-id="3625a-110">Di conseguenza, il caricatore di Common Language Runtime (CLR) ha più percorsi di codice per determinare l'assembly in cui risiede un modulo.</span><span class="sxs-lookup"><span data-stu-id="3625a-110">As a result, the common language runtime (CLR) loader has multiple code paths for determining the assembly in which a module lives.</span></span> <span data-ttu-id="3625a-111">Di conseguenza, è possibile che dopo la chiamata a [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) il modulo non conosca l'assembly in cui si trova e non sia possibile ottenere l'ID dell'assembly padre.</span><span class="sxs-lookup"><span data-stu-id="3625a-111">Therefore, it is possible that after [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) is called, the module does not know what assembly it is in and getting the parent assembly ID is not possible.</span></span> <span data-ttu-id="3625a-112">Il `ModuleAttachedToAssembly` metodo viene chiamato quando il modulo è associato al relativo assembly padre ed è possibile ottenere il relativo ID assembly padre.</span><span class="sxs-lookup"><span data-stu-id="3625a-112">The `ModuleAttachedToAssembly` method is called when the module is attached to its parent assembly and its parent assembly ID can be obtained.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3625a-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3625a-113">Requirements</span></span>  
 <span data-ttu-id="3625a-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3625a-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3625a-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3625a-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3625a-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3625a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3625a-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3625a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3625a-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3625a-118">See also</span></span>

- [<span data-ttu-id="3625a-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="3625a-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)

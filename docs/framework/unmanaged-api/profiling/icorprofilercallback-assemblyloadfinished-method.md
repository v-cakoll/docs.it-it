---
title: Metodo ICorProfilerCallback::AssemblyLoadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadFinished
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadFinished method [.NET Framework profiling]
- AssemblyLoadFinished method [.NET Framework profiling]
ms.assetid: 86d98f39-52e6-4c61-a625-9760f695ff12
topic_type:
- apiref
ms.openlocfilehash: ce4a842bc71ff144e46efb0d6f7068dfca9d207d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500442"
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a><span data-ttu-id="16d24-102">Metodo ICorProfilerCallback::AssemblyLoadFinished</span><span class="sxs-lookup"><span data-stu-id="16d24-102">ICorProfilerCallback::AssemblyLoadFinished Method</span></span>
<span data-ttu-id="16d24-103">Notifica al profiler che è stato completato il caricamento di un assembly.</span><span class="sxs-lookup"><span data-stu-id="16d24-103">Notifies the profiler that an assembly has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16d24-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="16d24-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16d24-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="16d24-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="16d24-106">\[in] identifica l'assembly caricato.</span><span class="sxs-lookup"><span data-stu-id="16d24-106">\[in] Identifies the assembly that was loaded.</span></span>

- `hrStatus`

  <span data-ttu-id="16d24-107">\[in] valore HRESULT che indica se il caricamento dell'assembly è stato completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="16d24-107">\[in] An HRESULT that indicates whether the assembly finished loading successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="16d24-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="16d24-108">Remarks</span></span>  
 <span data-ttu-id="16d24-109">Il valore di `assemblyId` non è valido per una richiesta di informazioni fino a quando non `AssemblyLoadFinished` viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="16d24-109">The value of `assemblyId` is not valid for an information request until the `AssemblyLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="16d24-110">Alcune parti del caricamento dell'assembly potrebbero continuare dopo il `AssemblyLoadFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="16d24-110">Some parts of loading the assembly might continue after the `AssemblyLoadFinished` callback.</span></span> <span data-ttu-id="16d24-111">Un errore HRESULT in `hrStatus` indica un errore.</span><span class="sxs-lookup"><span data-stu-id="16d24-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="16d24-112">Tuttavia, un HRESULT di esito positivo in `hrStatus` indica solo che la prima parte del caricamento dell'assembly ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="16d24-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16d24-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="16d24-113">Requirements</span></span>  
 <span data-ttu-id="16d24-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16d24-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16d24-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="16d24-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="16d24-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16d24-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16d24-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16d24-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16d24-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16d24-118">See also</span></span>

- [<span data-ttu-id="16d24-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="16d24-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)

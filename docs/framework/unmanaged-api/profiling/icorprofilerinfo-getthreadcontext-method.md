---
title: Metodo ICorProfilerInfo::GetThreadContext
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetThreadContext
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetThreadContext
helpviewer_keywords:
- ICorProfilerInfo::GetThreadContext method [.NET Framework profiling]
- GetThreadContext method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 79446216-4b8b-484c-8fe3-e87dbf9df2fd
topic_type:
- apiref
ms.openlocfilehash: 45ae164e79f077549a1d685aa060484240546a10
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497959"
---
# <a name="icorprofilerinfogetthreadcontext-method"></a><span data-ttu-id="63bd0-102">Metodo ICorProfilerInfo::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="63bd0-102">ICorProfilerInfo::GetThreadContext Method</span></span>
<span data-ttu-id="63bd0-103">Ottiene l'identità del contesto attualmente associata al thread specificato.</span><span class="sxs-lookup"><span data-stu-id="63bd0-103">Gets the context identity currently associated with the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63bd0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="63bd0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in]  ThreadID  threadId,  
    [out] ContextID *pContextId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63bd0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="63bd0-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="63bd0-106">in ID del thread.</span><span class="sxs-lookup"><span data-stu-id="63bd0-106">[in] The ID of the thread.</span></span>  
  
 `pContextId`  
 <span data-ttu-id="63bd0-107">out Puntatore all'ID del contesto attualmente associato al thread specificato.</span><span class="sxs-lookup"><span data-stu-id="63bd0-107">[out] A pointer to the context ID currently associated with the specified thread.</span></span> <span data-ttu-id="63bd0-108">Se al thread non è attualmente associato alcun contesto, questa funzione restituirà CORPROF_E_DATAINCOMPLETE.</span><span class="sxs-lookup"><span data-stu-id="63bd0-108">If the thread has no context currently associated with it, this function will return CORPROF_E_DATAINCOMPLETE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63bd0-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="63bd0-109">Requirements</span></span>  
 <span data-ttu-id="63bd0-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63bd0-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63bd0-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="63bd0-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="63bd0-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63bd0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63bd0-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63bd0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63bd0-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63bd0-114">See also</span></span>

- [<span data-ttu-id="63bd0-115">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="63bd0-115">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)

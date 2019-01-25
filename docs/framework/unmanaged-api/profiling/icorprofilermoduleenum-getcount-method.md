---
title: Metodo ICorProfilerModuleEnum::GetCount
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.GetCount Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::GetCount
helpviewer_keywords:
- ICorProfilerModuleEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: f0a4a5e0-4689-474b-b0f4-37ca0639c918
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c0d386dfa3e3ad8d60e239c82a84c648f2813696
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54572055"
---
# <a name="icorprofilermoduleenumgetcount-method"></a><span data-ttu-id="f739b-102">Metodo ICorProfilerModuleEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="f739b-102">ICorProfilerModuleEnum::GetCount Method</span></span>
<span data-ttu-id="f739b-103">Ottiene il numero di moduli gestiti caricati nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f739b-103">Gets the number of managed modules that were loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f739b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f739b-104">Syntax</span></span>  
  
```  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f739b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f739b-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="f739b-106">[out] Il numero di moduli CLR nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="f739b-106">[out] The number of runtime modules in the collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f739b-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f739b-107">Requirements</span></span>  
 <span data-ttu-id="f739b-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f739b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f739b-109">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f739b-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f739b-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f739b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f739b-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f739b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f739b-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f739b-112">See also</span></span>
- [<span data-ttu-id="f739b-113">Interfaccia ICorProfilerModuleEnum</span><span class="sxs-lookup"><span data-stu-id="f739b-113">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="f739b-114">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="f739b-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)

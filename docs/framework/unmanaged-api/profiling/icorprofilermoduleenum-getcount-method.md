---
title: Metodo ICorProfilerModuleEnum::GetCount
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerModuleEnum.GetCount Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerModuleEnum::GetCount
helpviewer_keywords:
- ICorProfilerModuleEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: f0a4a5e0-4689-474b-b0f4-37ca0639c918
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 930184a1d5c68ea87b2e3bc62b44a0176cd9db06
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilermoduleenumgetcount-method"></a><span data-ttu-id="dcf1a-102">Metodo ICorProfilerModuleEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="dcf1a-102">ICorProfilerModuleEnum::GetCount Method</span></span>
<span data-ttu-id="dcf1a-103">Ottiene il numero di moduli gestiti caricati nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="dcf1a-103">Gets the number of managed modules that were loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcf1a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dcf1a-104">Syntax</span></span>  
  
```  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dcf1a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dcf1a-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="dcf1a-106">[out] Il numero di moduli di runtime nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="dcf1a-106">[out] The number of runtime modules in the collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcf1a-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dcf1a-107">Requirements</span></span>  
 <span data-ttu-id="dcf1a-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dcf1a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcf1a-109">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dcf1a-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dcf1a-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dcf1a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dcf1a-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcf1a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcf1a-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dcf1a-112">See Also</span></span>  
 [<span data-ttu-id="dcf1a-113">ICorProfilerModuleEnum (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="dcf1a-113">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 [<span data-ttu-id="dcf1a-114">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="dcf1a-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)

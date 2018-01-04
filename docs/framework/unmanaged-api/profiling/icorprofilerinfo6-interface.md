---
title: Interfaccia ICorProfilerInfo6
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorProfilerInfo6
api_location: mscorwks.dll
api_type: COM
ms.assetid: 6f2bb148-1e2b-4e45-a5a5-0ceddc40064b
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 805f1e451b2c13c356d904c42dff87304aa2093c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo6-interface"></a><span data-ttu-id="a516d-102">Interfaccia ICorProfilerInfo6</span><span class="sxs-lookup"><span data-stu-id="a516d-102">ICorProfilerInfo6 Interface</span></span>
<span data-ttu-id="a516d-103">[Supportato in .NET Framework 4.6 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="a516d-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="a516d-104">Una sottoclasse di [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) che fornisce un enumeratore per tutti i metodi definiti in un modulo NGen specificato e un determinato metodo inline.</span><span class="sxs-lookup"><span data-stu-id="a516d-104">A subclass of [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) that provides an enumerator for all methods that are defined in a given NGen module and inline a given method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a516d-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="a516d-105">Methods</span></span>  
  
|<span data-ttu-id="a516d-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="a516d-106">Method</span></span>|<span data-ttu-id="a516d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a516d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a516d-108">Metodo ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod</span><span class="sxs-lookup"><span data-stu-id="a516d-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-enumngenmodulemethodsinliningthismethod-method.md)|<span data-ttu-id="a516d-109">Restituisce un enumeratore per tutti i metodi che appartengono a un determinato modulo NGen e che vengono impostati come inline nel corpo di un metodo specificato.</span><span class="sxs-lookup"><span data-stu-id="a516d-109">Returns an enumerator for all methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a516d-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a516d-110">Requirements</span></span>  
 <span data-ttu-id="a516d-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a516d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a516d-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a516d-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a516d-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a516d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a516d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a516d-114">See Also</span></span>  
 [<span data-ttu-id="a516d-115">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="a516d-115">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)

---
title: Interfaccia ICorProfilerInfo6
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo6
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 6f2bb148-1e2b-4e45-a5a5-0ceddc40064b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da1aab48e2eef229bb31e9443a5549c3f9fbc621
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455302"
---
# <a name="icorprofilerinfo6-interface"></a><span data-ttu-id="bb1cd-102">Interfaccia ICorProfilerInfo6</span><span class="sxs-lookup"><span data-stu-id="bb1cd-102">ICorProfilerInfo6 Interface</span></span>
<span data-ttu-id="bb1cd-103">[Supportato in .NET Framework 4.6 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="bb1cd-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="bb1cd-104">Una sottoclasse di [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) che fornisce un enumeratore per tutti i metodi definiti in un modulo NGen specificato e un determinato metodo inline.</span><span class="sxs-lookup"><span data-stu-id="bb1cd-104">A subclass of [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) that provides an enumerator for all methods that are defined in a given NGen module and inline a given method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bb1cd-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="bb1cd-105">Methods</span></span>  
  
|<span data-ttu-id="bb1cd-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="bb1cd-106">Method</span></span>|<span data-ttu-id="bb1cd-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb1cd-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bb1cd-108">Metodo ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod</span><span class="sxs-lookup"><span data-stu-id="bb1cd-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-enumngenmodulemethodsinliningthismethod-method.md)|<span data-ttu-id="bb1cd-109">Restituisce un enumeratore per tutti i metodi che appartengono a un determinato modulo NGen e che vengono impostati come inline nel corpo di un metodo specificato.</span><span class="sxs-lookup"><span data-stu-id="bb1cd-109">Returns an enumerator for all methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bb1cd-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bb1cd-110">Requirements</span></span>  
 <span data-ttu-id="bb1cd-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb1cd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb1cd-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bb1cd-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bb1cd-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb1cd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb1cd-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb1cd-114">See Also</span></span>  
 [<span data-ttu-id="bb1cd-115">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="bb1cd-115">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)

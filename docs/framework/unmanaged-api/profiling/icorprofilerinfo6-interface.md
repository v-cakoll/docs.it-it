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
ms.openlocfilehash: 80ac17a96e5c1c8c32cfc336da6c2be30eaf80fd
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868369"
---
# <a name="icorprofilerinfo6-interface"></a><span data-ttu-id="1c260-102">Interfaccia ICorProfilerInfo6</span><span class="sxs-lookup"><span data-stu-id="1c260-102">ICorProfilerInfo6 Interface</span></span>
<span data-ttu-id="1c260-103">[Supportato in .NET Framework 4,6 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="1c260-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="1c260-104">Sottoclasse di [ICorProfilerInfo5](icorprofilerinfo5-interface.md) che fornisce un enumeratore per tutti i metodi definiti in un determinato modulo NGen e inline di un metodo specificato.</span><span class="sxs-lookup"><span data-stu-id="1c260-104">A subclass of [ICorProfilerInfo5](icorprofilerinfo5-interface.md) that provides an enumerator for all methods that are defined in a given NGen module and inline a given method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1c260-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="1c260-105">Methods</span></span>  
  
|<span data-ttu-id="1c260-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="1c260-106">Method</span></span>|<span data-ttu-id="1c260-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1c260-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1c260-108">Metodo ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod</span><span class="sxs-lookup"><span data-stu-id="1c260-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>](icorprofilerinfo6-enumngenmodulemethodsinliningthismethod-method.md)|<span data-ttu-id="1c260-109">Restituisce un enumeratore per tutti i metodi che appartengono a un modulo NGen specificato e che sono inline nel corpo di un determinato metodo.</span><span class="sxs-lookup"><span data-stu-id="1c260-109">Returns an enumerator for all methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1c260-110">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="1c260-110">Requirements</span></span>  
 <span data-ttu-id="1c260-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c260-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c260-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1c260-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1c260-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c260-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c260-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c260-114">See also</span></span>

- [<span data-ttu-id="1c260-115">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="1c260-115">Profiling Interfaces</span></span>](profiling-interfaces.md)

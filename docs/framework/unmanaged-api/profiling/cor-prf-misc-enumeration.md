---
title: Enumerazione COR_PRF_MISC
ms.date: 03/30/2017
api_name:
- COR_PRF_MISC
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MISC
helpviewer_keywords:
- COR_PRF_MISC enumeration [.NET Framework profiling]
ms.assetid: 619bb5de-e309-48b6-a3af-32d935a0ff46
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3b40ac5f49288f7b30018e0c8c727e3ce6b73ae8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199492"
---
# <a name="corprfmisc-enumeration"></a><span data-ttu-id="88d27-102">Enumerazione COR_PRF_MISC</span><span class="sxs-lookup"><span data-stu-id="88d27-102">COR_PRF_MISC Enumeration</span></span>
<span data-ttu-id="88d27-103">Contiene valori costanti che specificano identificatori speciali.</span><span class="sxs-lookup"><span data-stu-id="88d27-103">Contains constant values that specify special identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88d27-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="88d27-104">Syntax</span></span>  
  
```  
typedef enum {  
    PROFILER_PARENT_UNKNOWN = 0xFFFFFFFD,  
    PROFILER_GLOBAL_CLASS   = 0xFFFFFFFE,  
    PROFILER_GLOBAL_MODULE  = 0xFFFFFFFF  
} COR_PRF_MISC;  
```  
  
## <a name="members"></a><span data-ttu-id="88d27-105">Membri</span><span class="sxs-lookup"><span data-stu-id="88d27-105">Members</span></span>  
  
|<span data-ttu-id="88d27-106">Member</span><span class="sxs-lookup"><span data-stu-id="88d27-106">Member</span></span>|<span data-ttu-id="88d27-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="88d27-107">Description</span></span>|  
|------------|-----------------|  
|`PROFILER_PARENT_UNKNOWN`|<span data-ttu-id="88d27-108">L'identificatore predefinito utilizzato dai [GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md) per un modulo che non è ancora stato associato a un assembly.</span><span class="sxs-lookup"><span data-stu-id="88d27-108">The default identifier used by [ICorProfilerInfo::GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md) for a module that has not yet been attached to an assembly.</span></span>|  
|`PROFILER_GLOBAL_CLASS`|<span data-ttu-id="88d27-109">L'identificatore di classe predefinito per le costanti globali che non appartengono a una classe.</span><span class="sxs-lookup"><span data-stu-id="88d27-109">The default class identifier for global constants that do not belong to a class.</span></span>|  
|`PROFILER_GLOBAL_MODULE`|<span data-ttu-id="88d27-110">L'identificatore del modulo predefinito per gli oggetti globali che non appartengono a un modulo.</span><span class="sxs-lookup"><span data-stu-id="88d27-110">The default module identifier for global objects that do not belong to a module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="88d27-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="88d27-111">Requirements</span></span>  
 <span data-ttu-id="88d27-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88d27-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88d27-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="88d27-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="88d27-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="88d27-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="88d27-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="88d27-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="88d27-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88d27-116">See also</span></span>

- [<span data-ttu-id="88d27-117">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="88d27-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)

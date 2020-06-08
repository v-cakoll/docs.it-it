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
ms.openlocfilehash: 7b8f2845589a8372f62c95ef1a82eae3ed602c1f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500832"
---
# <a name="cor_prf_misc-enumeration"></a><span data-ttu-id="457b1-102">Enumerazione COR_PRF_MISC</span><span class="sxs-lookup"><span data-stu-id="457b1-102">COR_PRF_MISC Enumeration</span></span>
<span data-ttu-id="457b1-103">Contiene valori costanti che specificano identificatori speciali.</span><span class="sxs-lookup"><span data-stu-id="457b1-103">Contains constant values that specify special identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="457b1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="457b1-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    PROFILER_PARENT_UNKNOWN = 0xFFFFFFFD,  
    PROFILER_GLOBAL_CLASS   = 0xFFFFFFFE,  
    PROFILER_GLOBAL_MODULE  = 0xFFFFFFFF  
} COR_PRF_MISC;  
```  
  
## <a name="members"></a><span data-ttu-id="457b1-105">Membri</span><span class="sxs-lookup"><span data-stu-id="457b1-105">Members</span></span>  
  
|<span data-ttu-id="457b1-106">Membro</span><span class="sxs-lookup"><span data-stu-id="457b1-106">Member</span></span>|<span data-ttu-id="457b1-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="457b1-107">Description</span></span>|  
|------------|-----------------|  
|`PROFILER_PARENT_UNKNOWN`|<span data-ttu-id="457b1-108">Identificatore predefinito usato da [ICorProfilerInfo:: GetModuleInfo](icorprofilerinfo-getmoduleinfo-method.md) per un modulo che non è ancora stato associato a un assembly.</span><span class="sxs-lookup"><span data-stu-id="457b1-108">The default identifier used by [ICorProfilerInfo::GetModuleInfo](icorprofilerinfo-getmoduleinfo-method.md) for a module that has not yet been attached to an assembly.</span></span>|  
|`PROFILER_GLOBAL_CLASS`|<span data-ttu-id="457b1-109">Identificatore di classe predefinito per le costanti globali che non appartengono a una classe.</span><span class="sxs-lookup"><span data-stu-id="457b1-109">The default class identifier for global constants that do not belong to a class.</span></span>|  
|`PROFILER_GLOBAL_MODULE`|<span data-ttu-id="457b1-110">Identificatore del modulo predefinito per gli oggetti globali che non appartengono a un modulo.</span><span class="sxs-lookup"><span data-stu-id="457b1-110">The default module identifier for global objects that do not belong to a module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="457b1-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="457b1-111">Requirements</span></span>  
 <span data-ttu-id="457b1-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="457b1-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="457b1-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="457b1-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="457b1-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="457b1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="457b1-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="457b1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="457b1-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="457b1-116">See also</span></span>

- [<span data-ttu-id="457b1-117">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="457b1-117">Profiling Enumerations</span></span>](profiling-enumerations.md)

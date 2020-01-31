---
title: Enumerazione COR_PRF_GC_REASON
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_REASON
helpviewer_keywords:
- COR_PRF_GC_REASON enumeration [.NET Framework profiling]
ms.assetid: 72822b95-a7fb-485e-9d55-1cb016d9a458
topic_type:
- apiref
ms.openlocfilehash: ec33e55f840fe735091364ebc35cb7b7c165c10a
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867185"
---
# <a name="cor_prf_gc_reason-enumeration"></a><span data-ttu-id="16624-102">Enumerazione COR_PRF_GC_REASON</span><span class="sxs-lookup"><span data-stu-id="16624-102">COR_PRF_GC_REASON Enumeration</span></span>
<span data-ttu-id="16624-103">Indica il motivo per cui è in corso la Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="16624-103">Indicates the reason that garbage collection is occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16624-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="16624-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_INDUCED = 1,  
    COR_PRF_GC_OTHER = 0  
} COR_PRF_GC_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="16624-105">Membri</span><span class="sxs-lookup"><span data-stu-id="16624-105">Members</span></span>  
  
|<span data-ttu-id="16624-106">Member</span><span class="sxs-lookup"><span data-stu-id="16624-106">Member</span></span>|<span data-ttu-id="16624-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="16624-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_INDUCED`|<span data-ttu-id="16624-108">Il Garbage Collection è stato indotto da un metodo di <xref:System.GC.Collect%2A>.</span><span class="sxs-lookup"><span data-stu-id="16624-108">The garbage collection was induced by a <xref:System.GC.Collect%2A> method.</span></span>|  
|`COR_PRF_GC_OTHER`|<span data-ttu-id="16624-109">Il motivo non è specificato.</span><span class="sxs-lookup"><span data-stu-id="16624-109">The reason is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="16624-110">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="16624-110">Requirements</span></span>  
 <span data-ttu-id="16624-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16624-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16624-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="16624-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="16624-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16624-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16624-114">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16624-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16624-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16624-115">See also</span></span>

- [<span data-ttu-id="16624-116">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="16624-116">Profiling Enumerations</span></span>](profiling-enumerations.md)

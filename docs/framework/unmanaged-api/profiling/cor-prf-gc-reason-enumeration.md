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
ms.openlocfilehash: 409a21238f172e5ecdaa8d5bfa237a9f3fe46345
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500910"
---
# <a name="cor_prf_gc_reason-enumeration"></a><span data-ttu-id="bf0c1-102">Enumerazione COR_PRF_GC_REASON</span><span class="sxs-lookup"><span data-stu-id="bf0c1-102">COR_PRF_GC_REASON Enumeration</span></span>
<span data-ttu-id="bf0c1-103">Indica il motivo per cui è in corso la Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="bf0c1-103">Indicates the reason that garbage collection is occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf0c1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bf0c1-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_INDUCED = 1,  
    COR_PRF_GC_OTHER = 0  
} COR_PRF_GC_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="bf0c1-105">Membri</span><span class="sxs-lookup"><span data-stu-id="bf0c1-105">Members</span></span>  
  
|<span data-ttu-id="bf0c1-106">Membro</span><span class="sxs-lookup"><span data-stu-id="bf0c1-106">Member</span></span>|<span data-ttu-id="bf0c1-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bf0c1-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_INDUCED`|<span data-ttu-id="bf0c1-108">Il Garbage Collection è stato indotto da un <xref:System.GC.Collect%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="bf0c1-108">The garbage collection was induced by a <xref:System.GC.Collect%2A> method.</span></span>|  
|`COR_PRF_GC_OTHER`|<span data-ttu-id="bf0c1-109">Il motivo non è specificato.</span><span class="sxs-lookup"><span data-stu-id="bf0c1-109">The reason is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bf0c1-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bf0c1-110">Requirements</span></span>  
 <span data-ttu-id="bf0c1-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf0c1-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf0c1-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bf0c1-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bf0c1-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf0c1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf0c1-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf0c1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf0c1-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf0c1-115">See also</span></span>

- [<span data-ttu-id="bf0c1-116">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="bf0c1-116">Profiling Enumerations</span></span>](profiling-enumerations.md)

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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: daf97f25b1adc30b173fcd81812a4b197915cdd1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775045"
---
# <a name="corprfgcreason-enumeration"></a><span data-ttu-id="86e26-102">Enumerazione COR_PRF_GC_REASON</span><span class="sxs-lookup"><span data-stu-id="86e26-102">COR_PRF_GC_REASON Enumeration</span></span>
<span data-ttu-id="86e26-103">Indica il motivo per cui è in corso la Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="86e26-103">Indicates the reason that garbage collection is occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86e26-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="86e26-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_INDUCED = 1,  
    COR_PRF_GC_OTHER = 0  
} COR_PRF_GC_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="86e26-105">Membri</span><span class="sxs-lookup"><span data-stu-id="86e26-105">Members</span></span>  
  
|<span data-ttu-id="86e26-106">Member</span><span class="sxs-lookup"><span data-stu-id="86e26-106">Member</span></span>|<span data-ttu-id="86e26-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="86e26-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_INDUCED`|<span data-ttu-id="86e26-108">L'operazione di garbage collection è stata causata da un <xref:System.GC.Collect%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="86e26-108">The garbage collection was induced by a <xref:System.GC.Collect%2A> method.</span></span>|  
|`COR_PRF_GC_OTHER`|<span data-ttu-id="86e26-109">Il motivo è specificato.</span><span class="sxs-lookup"><span data-stu-id="86e26-109">The reason is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="86e26-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="86e26-110">Requirements</span></span>  
 <span data-ttu-id="86e26-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86e26-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86e26-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="86e26-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="86e26-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86e26-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86e26-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86e26-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86e26-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86e26-115">See also</span></span>

- [<span data-ttu-id="86e26-116">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="86e26-116">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)

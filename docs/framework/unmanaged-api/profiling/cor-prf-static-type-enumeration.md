---
title: Enumerazione COR_PRF_STATIC_TYPE
ms.date: 03/30/2017
api_name:
- COR_PRF_STATIC_TYPE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_STATIC_TYPE
helpviewer_keywords:
- COR_PRF_STATIC_TYPE enumeration [.NET Framework profiling]
ms.assetid: 441d7809-5b65-41a5-ba64-2910a8008315
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 310915ce84819a2a5a2d5e1f22356b61c16e7ec7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59190496"
---
# <a name="corprfstatictype-enumeration"></a><span data-ttu-id="f19a3-102">Enumerazione COR_PRF_STATIC_TYPE</span><span class="sxs-lookup"><span data-stu-id="f19a3-102">COR_PRF_STATIC_TYPE Enumeration</span></span>
<span data-ttu-id="f19a3-103">Indica se un campo è statico e, in tal caso, la qualità statica che si applica al campo.</span><span class="sxs-lookup"><span data-stu-id="f19a3-103">Indicates whether a field is static and, if so, the static quality that applies to the field.</span></span> <span data-ttu-id="f19a3-104">Questi valori possono essere combinati utilizzando l'operatore OR bit per indicare che il campo dispone di più, la qualità statica diverse.</span><span class="sxs-lookup"><span data-stu-id="f19a3-104">These values can be combined using the bitwise OR operation to indicate that the field has multiple, different static qualities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f19a3-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f19a3-105">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_FIELD_NOT_A_STATIC = 0x0,  
    COR_PRF_FIELD_APP_DOMAIN_STATIC = 0x1,  
    COR_PRF_FIELD_THREAD_STATIC = 0x2,  
    COR_PRF_FIELD_CONTEXT_STATIC = 0x4,  
    COR_PRF_FIELD_RVA_STATIC = 0x8  
} COR_PRF_STATIC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="f19a3-106">Membri</span><span class="sxs-lookup"><span data-stu-id="f19a3-106">Members</span></span>  
  
|<span data-ttu-id="f19a3-107">Member</span><span class="sxs-lookup"><span data-stu-id="f19a3-107">Member</span></span>|<span data-ttu-id="f19a3-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f19a3-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_NOT_A_STATIC`|<span data-ttu-id="f19a3-109">Il campo non è statico.</span><span class="sxs-lookup"><span data-stu-id="f19a3-109">The field is not static.</span></span>|  
|`COR_PRF_FIELD_APP_DOMAIN_STATIC`|<span data-ttu-id="f19a3-110">Il campo è statico dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="f19a3-110">The field is application domain-static.</span></span>|  
|`COR_PRF_FIELD_THREAD_STATIC`|<span data-ttu-id="f19a3-111">Il campo è statico.</span><span class="sxs-lookup"><span data-stu-id="f19a3-111">The field is thread-static.</span></span>|  
|`COR_PRF_FIELD_CONTEXT_STATIC`|<span data-ttu-id="f19a3-112">Il campo è statico.</span><span class="sxs-lookup"><span data-stu-id="f19a3-112">The field is context-static.</span></span>|  
|`COR_PRF_FIELD_RVA_STATIC`|<span data-ttu-id="f19a3-113">Il campo è un indirizzo virtuale relativo (RVA)-statici.</span><span class="sxs-lookup"><span data-stu-id="f19a3-113">The field is relative virtual address (RVA)-static.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f19a3-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f19a3-114">Requirements</span></span>  
 <span data-ttu-id="f19a3-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f19a3-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f19a3-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f19a3-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f19a3-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f19a3-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f19a3-118">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f19a3-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f19a3-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f19a3-119">See also</span></span>

- [<span data-ttu-id="f19a3-120">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="f19a3-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)

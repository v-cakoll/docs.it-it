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
ms.openlocfilehash: 880c9bd186d6cb2acb277e9cc55d3063fb8d51d8
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867035"
---
# <a name="cor_prf_static_type-enumeration"></a><span data-ttu-id="f6577-102">Enumerazione COR_PRF_STATIC_TYPE</span><span class="sxs-lookup"><span data-stu-id="f6577-102">COR_PRF_STATIC_TYPE Enumeration</span></span>
<span data-ttu-id="f6577-103">Indica se un campo è statico e, in tal caso, la qualità statica che si applica al campo.</span><span class="sxs-lookup"><span data-stu-id="f6577-103">Indicates whether a field is static and, if so, the static quality that applies to the field.</span></span> <span data-ttu-id="f6577-104">Questi valori possono essere combinati usando l'operazione OR bit per bit per indicare che il campo ha più qualità statiche diverse.</span><span class="sxs-lookup"><span data-stu-id="f6577-104">These values can be combined using the bitwise OR operation to indicate that the field has multiple, different static qualities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6577-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f6577-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_FIELD_NOT_A_STATIC = 0x0,  
    COR_PRF_FIELD_APP_DOMAIN_STATIC = 0x1,  
    COR_PRF_FIELD_THREAD_STATIC = 0x2,  
    COR_PRF_FIELD_CONTEXT_STATIC = 0x4,  
    COR_PRF_FIELD_RVA_STATIC = 0x8  
} COR_PRF_STATIC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="f6577-106">Membri</span><span class="sxs-lookup"><span data-stu-id="f6577-106">Members</span></span>  
  
|<span data-ttu-id="f6577-107">Member</span><span class="sxs-lookup"><span data-stu-id="f6577-107">Member</span></span>|<span data-ttu-id="f6577-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f6577-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_NOT_A_STATIC`|<span data-ttu-id="f6577-109">Il campo non è statico.</span><span class="sxs-lookup"><span data-stu-id="f6577-109">The field is not static.</span></span>|  
|`COR_PRF_FIELD_APP_DOMAIN_STATIC`|<span data-ttu-id="f6577-110">Il campo è statico del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f6577-110">The field is application domain-static.</span></span>|  
|`COR_PRF_FIELD_THREAD_STATIC`|<span data-ttu-id="f6577-111">Il campo è di thread-static.</span><span class="sxs-lookup"><span data-stu-id="f6577-111">The field is thread-static.</span></span>|  
|`COR_PRF_FIELD_CONTEXT_STATIC`|<span data-ttu-id="f6577-112">Il campo è statico del contesto.</span><span class="sxs-lookup"><span data-stu-id="f6577-112">The field is context-static.</span></span>|  
|`COR_PRF_FIELD_RVA_STATIC`|<span data-ttu-id="f6577-113">Il campo è un indirizzo RVA (relativo Virtual Address), statico.</span><span class="sxs-lookup"><span data-stu-id="f6577-113">The field is relative virtual address (RVA)-static.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f6577-114">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="f6577-114">Requirements</span></span>  
 <span data-ttu-id="f6577-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6577-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6577-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f6577-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f6577-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6577-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6577-118">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6577-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6577-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6577-119">See also</span></span>

- [<span data-ttu-id="f6577-120">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="f6577-120">Profiling Enumerations</span></span>](profiling-enumerations.md)

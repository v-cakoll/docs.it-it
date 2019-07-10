---
title: Enumerazione COR_PRF_RUNTIME_TYPE
ms.date: 03/30/2017
api_name:
- COR_PRF_RUNTIME_TYPE Enumeration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_RUNTIME_TYPE
helpviewer_keywords:
- COR_PRF_RUNTIME_TYPE enumeration [.NET Framework profiling]
ms.assetid: 35449514-333f-4918-9c60-7aa198d655d2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6c52f96ad9458dfd5cdedc5cc73154aa570c6759
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751969"
---
# <a name="corprfruntimetype-enumeration"></a><span data-ttu-id="8cb6a-102">Enumerazione COR_PRF_RUNTIME_TYPE</span><span class="sxs-lookup"><span data-stu-id="8cb6a-102">COR_PRF_RUNTIME_TYPE Enumeration</span></span>
<span data-ttu-id="8cb6a-103">Contiene valori che indicano la versione di common language runtime (CLR): desktop o CoreCLR, che viene usato in Silverlight.</span><span class="sxs-lookup"><span data-stu-id="8cb6a-103">Contains values that indicate the version of the common language runtime (CLR): desktop or CoreCLR, which is used in Silverlight.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cb6a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8cb6a-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    COR_PRF_DESKTOP_CLR = 0x1,  
    COR_PRF_CORE_CLR    = 0x2,  
} COR_PRF_RUNTIME_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="8cb6a-105">Membri</span><span class="sxs-lookup"><span data-stu-id="8cb6a-105">Members</span></span>  
  
|<span data-ttu-id="8cb6a-106">Member</span><span class="sxs-lookup"><span data-stu-id="8cb6a-106">Member</span></span>|<span data-ttu-id="8cb6a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8cb6a-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DESKTOP_CLR`|<span data-ttu-id="8cb6a-108">La versione desktop di CLR.</span><span class="sxs-lookup"><span data-stu-id="8cb6a-108">The desktop version of the CLR.</span></span>|  
|`COR_PRF_CORE_CLR`|<span data-ttu-id="8cb6a-109">La versione di base di CLR, usato in Silverlight.</span><span class="sxs-lookup"><span data-stu-id="8cb6a-109">The core version of the CLR, used in Silverlight.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8cb6a-110">Note</span><span class="sxs-lookup"><span data-stu-id="8cb6a-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cb6a-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8cb6a-111">Requirements</span></span>  
 <span data-ttu-id="8cb6a-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8cb6a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cb6a-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8cb6a-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8cb6a-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8cb6a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8cb6a-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cb6a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cb6a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8cb6a-116">See also</span></span>

- [<span data-ttu-id="8cb6a-117">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="8cb6a-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)

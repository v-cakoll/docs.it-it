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
ms.openlocfilehash: e57c622780f0bc92061fd2928ea861f904d9eb37
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122109"
---
# <a name="corprfruntimetype-enumeration"></a><span data-ttu-id="4db3c-102">Enumerazione COR_PRF_RUNTIME_TYPE</span><span class="sxs-lookup"><span data-stu-id="4db3c-102">COR_PRF_RUNTIME_TYPE Enumeration</span></span>
<span data-ttu-id="4db3c-103">Contiene valori che indicano la versione di common language runtime (CLR): desktop o CoreCLR, che viene usato in Silverlight.</span><span class="sxs-lookup"><span data-stu-id="4db3c-103">Contains values that indicate the version of the common language runtime (CLR): desktop or CoreCLR, which is used in Silverlight.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4db3c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4db3c-104">Syntax</span></span>  
  
```  
typedef enum  
{  
    COR_PRF_DESKTOP_CLR = 0x1,  
    COR_PRF_CORE_CLR    = 0x2,  
} COR_PRF_RUNTIME_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="4db3c-105">Membri</span><span class="sxs-lookup"><span data-stu-id="4db3c-105">Members</span></span>  
  
|<span data-ttu-id="4db3c-106">Member</span><span class="sxs-lookup"><span data-stu-id="4db3c-106">Member</span></span>|<span data-ttu-id="4db3c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4db3c-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DESKTOP_CLR`|<span data-ttu-id="4db3c-108">La versione desktop di CLR.</span><span class="sxs-lookup"><span data-stu-id="4db3c-108">The desktop version of the CLR.</span></span>|  
|`COR_PRF_CORE_CLR`|<span data-ttu-id="4db3c-109">La versione di base di CLR, usato in Silverlight.</span><span class="sxs-lookup"><span data-stu-id="4db3c-109">The core version of the CLR, used in Silverlight.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4db3c-110">Note</span><span class="sxs-lookup"><span data-stu-id="4db3c-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4db3c-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4db3c-111">Requirements</span></span>  
 <span data-ttu-id="4db3c-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4db3c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4db3c-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4db3c-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4db3c-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4db3c-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="4db3c-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="4db3c-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4db3c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4db3c-116">See also</span></span>

- [<span data-ttu-id="4db3c-117">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="4db3c-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)

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
ms.openlocfilehash: 28e6e95bbcca35ad39f30adcf100519748c02838
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449998"
---
# <a name="corprfruntimetype-enumeration"></a><span data-ttu-id="2c70e-102">Enumerazione COR_PRF_RUNTIME_TYPE</span><span class="sxs-lookup"><span data-stu-id="2c70e-102">COR_PRF_RUNTIME_TYPE Enumeration</span></span>
<span data-ttu-id="2c70e-103">Contiene valori che indicano la versione di common language runtime (CLR): desktop o CoreCLR, che viene utilizzato in Silverlight.</span><span class="sxs-lookup"><span data-stu-id="2c70e-103">Contains values that indicate the version of the common language runtime (CLR): desktop or CoreCLR, which is used in Silverlight.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c70e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2c70e-104">Syntax</span></span>  
  
```  
typedef enum  
{  
    COR_PRF_DESKTOP_CLR = 0x1,  
    COR_PRF_CORE_CLR    = 0x2,  
} COR_PRF_RUNTIME_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="2c70e-105">Membri</span><span class="sxs-lookup"><span data-stu-id="2c70e-105">Members</span></span>  
  
|<span data-ttu-id="2c70e-106">Membro</span><span class="sxs-lookup"><span data-stu-id="2c70e-106">Member</span></span>|<span data-ttu-id="2c70e-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c70e-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DESKTOP_CLR`|<span data-ttu-id="2c70e-108">La versione desktop di CLR.</span><span class="sxs-lookup"><span data-stu-id="2c70e-108">The desktop version of the CLR.</span></span>|  
|`COR_PRF_CORE_CLR`|<span data-ttu-id="2c70e-109">La versione principale di CLR, utilizzata in Silverlight.</span><span class="sxs-lookup"><span data-stu-id="2c70e-109">The core version of the CLR, used in Silverlight.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c70e-110">Note</span><span class="sxs-lookup"><span data-stu-id="2c70e-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c70e-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2c70e-111">Requirements</span></span>  
 <span data-ttu-id="2c70e-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c70e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c70e-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2c70e-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2c70e-114">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="2c70e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c70e-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c70e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c70e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c70e-116">See Also</span></span>  
 [<span data-ttu-id="2c70e-117">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="2c70e-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)

---
title: Enumerazione COR_PUB_ENUMPROCESS
ms.date: 03/30/2017
api_name:
- COR_PUB_ENUMPROCESS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_PUB_ENUMPROCESS
helpviewer_keywords:
- COR_PUB_ENUMPROCESS enumeration [.NET Framework debugging]
ms.assetid: 5d3ada6e-feea-47da-a7ed-b664107c137f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 02ff60852a85d003deb68cae96a184ac8d61c65f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089412"
---
# <a name="corpubenumprocess-enumeration"></a><span data-ttu-id="3a3f9-102">Enumerazione COR_PUB_ENUMPROCESS</span><span class="sxs-lookup"><span data-stu-id="3a3f9-102">COR_PUB_ENUMPROCESS Enumeration</span></span>
<span data-ttu-id="3a3f9-103">Identifica il tipo di processo da enumerare.</span><span class="sxs-lookup"><span data-stu-id="3a3f9-103">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a3f9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3a3f9-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="3a3f9-105">Membri</span><span class="sxs-lookup"><span data-stu-id="3a3f9-105">Members</span></span>  
  
|<span data-ttu-id="3a3f9-106">Nome del membro</span><span class="sxs-lookup"><span data-stu-id="3a3f9-106">Member name</span></span>|<span data-ttu-id="3a3f9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a3f9-107">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="3a3f9-108">Un processo gestito.</span><span class="sxs-lookup"><span data-stu-id="3a3f9-108">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a3f9-109">Note</span><span class="sxs-lookup"><span data-stu-id="3a3f9-109">Remarks</span></span>  
 <span data-ttu-id="3a3f9-110">La versione corrente dell'API di debug non gestito enumera solo i processi gestiti.</span><span class="sxs-lookup"><span data-stu-id="3a3f9-110">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a3f9-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3a3f9-111">Requirements</span></span>  
 <span data-ttu-id="3a3f9-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a3f9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a3f9-113">**Intestazione:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="3a3f9-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="3a3f9-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a3f9-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3a3f9-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3a3f9-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3a3f9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a3f9-116">See also</span></span>

- [<span data-ttu-id="3a3f9-117">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="3a3f9-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

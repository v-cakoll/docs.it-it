---
title: Enumerazione CLSID_RESOLUTION_FLAGS
ms.date: 03/30/2017
api_name:
- CLSID_RESOLUTION_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CLSID_RESOLUTION_FLAGS
helpviewer_keywords:
- CLSID_RESOLUTION_FLAGS enumeration [.NET Framework hosting]
ms.assetid: cd8b9879-962a-4811-aa46-2e2b6bae0d84
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bee25122920a6fcec3bbd4e9e53bbdad008d5304
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54514105"
---
# <a name="clsidresolutionflags-enumeration"></a><span data-ttu-id="31ee3-102">Enumerazione CLSID_RESOLUTION_FLAGS</span><span class="sxs-lookup"><span data-stu-id="31ee3-102">CLSID_RESOLUTION_FLAGS Enumeration</span></span>
<span data-ttu-id="31ee3-103">Contiene valori che indicano come common language runtime (CLR) è necessario risolvere una `CLSID`.</span><span class="sxs-lookup"><span data-stu-id="31ee3-103">Contains values that indicate how the common language runtime (CLR) should resolve a `CLSID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31ee3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="31ee3-104">Syntax</span></span>  
  
```  
typedef enum {  
    CLSID_RESOLUTION_DEFAULT      = 0x0,  
    CLSID_RESOLUTION_REGISTERED   = 0x1  
} CLSID_RESOLUTION_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="31ee3-105">Membri</span><span class="sxs-lookup"><span data-stu-id="31ee3-105">Members</span></span>  
  
|<span data-ttu-id="31ee3-106">Membro</span><span class="sxs-lookup"><span data-stu-id="31ee3-106">Member</span></span>|<span data-ttu-id="31ee3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="31ee3-107">Description</span></span>|  
|------------|-----------------|  
|`CLSID_RESOLUTION_DEFAULT`|<span data-ttu-id="31ee3-108">Indica il comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="31ee3-108">Indicates the default behavior.</span></span>|  
|`CLSID_RESOLUTION_REGISTERED`|<span data-ttu-id="31ee3-109">Indica che il runtime cerca il Registro di sistema e applica i criteri di shim.</span><span class="sxs-lookup"><span data-stu-id="31ee3-109">Indicates that the runtime searches the registry and applies shim policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="31ee3-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="31ee3-110">Requirements</span></span>  
 <span data-ttu-id="31ee3-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31ee3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31ee3-112">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="31ee3-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="31ee3-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31ee3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31ee3-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31ee3-114">See also</span></span>
- [<span data-ttu-id="31ee3-115">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="31ee3-115">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)

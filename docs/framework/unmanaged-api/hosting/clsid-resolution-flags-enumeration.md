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
ms.openlocfilehash: d52f9f0bc2ff27d7849a80a424714aa84d3688fe
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137001"
---
# <a name="clsid_resolution_flags-enumeration"></a><span data-ttu-id="317b0-102">Enumerazione CLSID_RESOLUTION_FLAGS</span><span class="sxs-lookup"><span data-stu-id="317b0-102">CLSID_RESOLUTION_FLAGS Enumeration</span></span>
<span data-ttu-id="317b0-103">Contiene valori che indicano il modo in cui il Common Language Runtime (CLR) deve risolvere una `CLSID`.</span><span class="sxs-lookup"><span data-stu-id="317b0-103">Contains values that indicate how the common language runtime (CLR) should resolve a `CLSID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="317b0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="317b0-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    CLSID_RESOLUTION_DEFAULT      = 0x0,  
    CLSID_RESOLUTION_REGISTERED   = 0x1  
} CLSID_RESOLUTION_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="317b0-105">Members</span><span class="sxs-lookup"><span data-stu-id="317b0-105">Members</span></span>  
  
|<span data-ttu-id="317b0-106">Member</span><span class="sxs-lookup"><span data-stu-id="317b0-106">Member</span></span>|<span data-ttu-id="317b0-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="317b0-107">Description</span></span>|  
|------------|-----------------|  
|`CLSID_RESOLUTION_DEFAULT`|<span data-ttu-id="317b0-108">Indica il comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="317b0-108">Indicates the default behavior.</span></span>|  
|`CLSID_RESOLUTION_REGISTERED`|<span data-ttu-id="317b0-109">Indica che il runtime cerca nel registro di sistema e applica i criteri di shim.</span><span class="sxs-lookup"><span data-stu-id="317b0-109">Indicates that the runtime searches the registry and applies shim policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="317b0-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="317b0-110">Requirements</span></span>  
 <span data-ttu-id="317b0-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="317b0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="317b0-112">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="317b0-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="317b0-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="317b0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="317b0-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="317b0-114">See also</span></span>

- [<span data-ttu-id="317b0-115">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="317b0-115">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)

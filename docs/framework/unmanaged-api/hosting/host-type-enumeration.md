---
title: Enumerazione HOST_TYPE
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- HOST_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- HOST_TYPE
helpviewer_keywords:
- HOST_TYPE enumeration [.NET Framework hosting]
ms.assetid: 51f848be-84c5-4036-9839-c762c576bbf5
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a8c910dd06109a8a69f29517812737d4b4dcef21
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="hosttype-enumeration"></a><span data-ttu-id="682fe-102">Enumerazione HOST_TYPE</span><span class="sxs-lookup"><span data-stu-id="682fe-102">HOST_TYPE Enumeration</span></span>
<span data-ttu-id="682fe-103">Contiene valori che specificano il tipo di host che esegue un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="682fe-103">Contains values that specify the type of host that is launching an application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="682fe-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="682fe-104">Syntax</span></span>  
  
```  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="682fe-105">Membri</span><span class="sxs-lookup"><span data-stu-id="682fe-105">Members</span></span>  
  
|<span data-ttu-id="682fe-106">Membro</span><span class="sxs-lookup"><span data-stu-id="682fe-106">Member</span></span>|<span data-ttu-id="682fe-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="682fe-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|<span data-ttu-id="682fe-108">Avviare l'applicazione da AppLaunch.exe.</span><span class="sxs-lookup"><span data-stu-id="682fe-108">Launch the application from AppLaunch.exe.</span></span><br /><br /> <span data-ttu-id="682fe-109">Utilizzare questo valore per le applicazioni parzialmente attendibili.</span><span class="sxs-lookup"><span data-stu-id="682fe-109">Use this value for partially-trusted applications.</span></span>|  
|`HOST_TYPE_CORFLAG`|<span data-ttu-id="682fe-110">Avviare l'applicazione direttamente.</span><span class="sxs-lookup"><span data-stu-id="682fe-110">Launch the application directly.</span></span> <span data-ttu-id="682fe-111">Vale a dire, avviare l'applicazione dal file .exe.</span><span class="sxs-lookup"><span data-stu-id="682fe-111">That is, launch the application from its own .exe file.</span></span><br /><br /> <span data-ttu-id="682fe-112">Utilizzare questo valore per le applicazioni completamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="682fe-112">Use this value for fully-trusted applications.</span></span>|  
|`HOST_TYPE_DEFAULT`|<span data-ttu-id="682fe-113">Uguale a HOST_TYPE_APPLAUNCH.</span><span class="sxs-lookup"><span data-stu-id="682fe-113">Same as HOST_TYPE_APPLAUNCH.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="682fe-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="682fe-114">Requirements</span></span>  
 <span data-ttu-id="682fe-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="682fe-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="682fe-116">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="682fe-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="682fe-117">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="682fe-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="682fe-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="682fe-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="682fe-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="682fe-119">See Also</span></span>  
 [<span data-ttu-id="682fe-120">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="682fe-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)

---
title: Enumerazione CorDebugHandleType
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugHandleType
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugHandleType
helpviewer_keywords: CorDebugHandleType enumeration [.NET Framework debugging]
ms.assetid: 84296b55-c2c5-424c-ac9c-8e28e2895945
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 408c66bd33ba12b2c674dd6c4a049acfb8c4c986
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="cordebughandletype-enumeration"></a><span data-ttu-id="9804a-102">Enumerazione CorDebugHandleType</span><span class="sxs-lookup"><span data-stu-id="9804a-102">CorDebugHandleType Enumeration</span></span>
<span data-ttu-id="9804a-103">Indica il tipo di handle.</span><span class="sxs-lookup"><span data-stu-id="9804a-103">Indicates the handle type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9804a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9804a-104">Syntax</span></span>  
  
```  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a><span data-ttu-id="9804a-105">Membri</span><span class="sxs-lookup"><span data-stu-id="9804a-105">Members</span></span>  
  
|<span data-ttu-id="9804a-106">Membro</span><span class="sxs-lookup"><span data-stu-id="9804a-106">Member</span></span>|<span data-ttu-id="9804a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9804a-107">Description</span></span>|  
|------------|-----------------|  
|`HANDLE_STRONG`|<span data-ttu-id="9804a-108">L'handle è forte, che impedisce un oggetto viene recuperato da garbage collection.</span><span class="sxs-lookup"><span data-stu-id="9804a-108">The handle is strong, which prevents an object from being reclaimed by garbage collection.</span></span>|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|<span data-ttu-id="9804a-109">L'handle è debole, che non impedisce un oggetto viene recuperato da garbage collection.</span><span class="sxs-lookup"><span data-stu-id="9804a-109">The handle is weak, which does not prevent an object from being reclaimed by garbage collection.</span></span><br /><br /> <span data-ttu-id="9804a-110">L'handle viene invalidato quando l'oggetto viene raccolto.</span><span class="sxs-lookup"><span data-stu-id="9804a-110">The handle becomes invalid when the object is collected.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9804a-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9804a-111">Requirements</span></span>  
 <span data-ttu-id="9804a-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9804a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9804a-113">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="9804a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9804a-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9804a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9804a-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9804a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9804a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9804a-116">See Also</span></span>  
 [<span data-ttu-id="9804a-117">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="9804a-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

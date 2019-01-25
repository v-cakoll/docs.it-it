---
title: Enumerazione CorDebugHandleType
ms.date: 03/30/2017
api_name:
- CorDebugHandleType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugHandleType
helpviewer_keywords:
- CorDebugHandleType enumeration [.NET Framework debugging]
ms.assetid: 84296b55-c2c5-424c-ac9c-8e28e2895945
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5ca7508c675ccc4c4ee0c07a2d7790bb5de7a668
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54594590"
---
# <a name="cordebughandletype-enumeration"></a><span data-ttu-id="2c1d8-102">Enumerazione CorDebugHandleType</span><span class="sxs-lookup"><span data-stu-id="2c1d8-102">CorDebugHandleType Enumeration</span></span>
<span data-ttu-id="2c1d8-103">Indica il tipo di handle.</span><span class="sxs-lookup"><span data-stu-id="2c1d8-103">Indicates the handle type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c1d8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2c1d8-104">Syntax</span></span>  
  
```  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a><span data-ttu-id="2c1d8-105">Membri</span><span class="sxs-lookup"><span data-stu-id="2c1d8-105">Members</span></span>  
  
|<span data-ttu-id="2c1d8-106">Membro</span><span class="sxs-lookup"><span data-stu-id="2c1d8-106">Member</span></span>|<span data-ttu-id="2c1d8-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c1d8-107">Description</span></span>|  
|------------|-----------------|  
|`HANDLE_STRONG`|<span data-ttu-id="2c1d8-108">L'handle è forte, che impedisce un oggetto viene recuperato da garbage collection.</span><span class="sxs-lookup"><span data-stu-id="2c1d8-108">The handle is strong, which prevents an object from being reclaimed by garbage collection.</span></span>|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|<span data-ttu-id="2c1d8-109">L'handle è debole, che non impedisce un oggetto viene recuperato da garbage collection.</span><span class="sxs-lookup"><span data-stu-id="2c1d8-109">The handle is weak, which does not prevent an object from being reclaimed by garbage collection.</span></span><br /><br /> <span data-ttu-id="2c1d8-110">L'handle viene invalidato quando l'oggetto viene raccolto.</span><span class="sxs-lookup"><span data-stu-id="2c1d8-110">The handle becomes invalid when the object is collected.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2c1d8-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2c1d8-111">Requirements</span></span>  
 <span data-ttu-id="2c1d8-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c1d8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c1d8-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c1d8-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c1d8-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c1d8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c1d8-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c1d8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c1d8-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c1d8-116">See also</span></span>
- [<span data-ttu-id="2c1d8-117">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="2c1d8-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

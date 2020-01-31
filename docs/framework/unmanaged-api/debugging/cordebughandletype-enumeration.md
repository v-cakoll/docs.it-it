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
ms.openlocfilehash: 15572037940f7c45ec5dcb7e34599756e15fd3bd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793904"
---
# <a name="cordebughandletype-enumeration"></a><span data-ttu-id="f2ea8-102">Enumerazione CorDebugHandleType</span><span class="sxs-lookup"><span data-stu-id="f2ea8-102">CorDebugHandleType Enumeration</span></span>
<span data-ttu-id="f2ea8-103">Indica il tipo di handle.</span><span class="sxs-lookup"><span data-stu-id="f2ea8-103">Indicates the handle type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2ea8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f2ea8-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a><span data-ttu-id="f2ea8-105">Membri</span><span class="sxs-lookup"><span data-stu-id="f2ea8-105">Members</span></span>  
  
|<span data-ttu-id="f2ea8-106">Member</span><span class="sxs-lookup"><span data-stu-id="f2ea8-106">Member</span></span>|<span data-ttu-id="f2ea8-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f2ea8-107">Description</span></span>|  
|------------|-----------------|  
|`HANDLE_STRONG`|<span data-ttu-id="f2ea8-108">Il punto di controllo è sicuro e impedisce a un oggetto di essere recuperato da Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="f2ea8-108">The handle is strong, which prevents an object from being reclaimed by garbage collection.</span></span>|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|<span data-ttu-id="f2ea8-109">L'handle è debole, che non impedisce che un oggetto venga recuperato dal Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="f2ea8-109">The handle is weak, which does not prevent an object from being reclaimed by garbage collection.</span></span><br /><br /> <span data-ttu-id="f2ea8-110">Quando l'oggetto viene raccolto, l'handle diventa non valido.</span><span class="sxs-lookup"><span data-stu-id="f2ea8-110">The handle becomes invalid when the object is collected.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f2ea8-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="f2ea8-111">Requirements</span></span>  
 <span data-ttu-id="f2ea8-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2ea8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2ea8-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f2ea8-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2ea8-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2ea8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2ea8-115">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2ea8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2ea8-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2ea8-116">See also</span></span>

- [<span data-ttu-id="f2ea8-117">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="f2ea8-117">Debugging Enumerations</span></span>](debugging-enumerations.md)

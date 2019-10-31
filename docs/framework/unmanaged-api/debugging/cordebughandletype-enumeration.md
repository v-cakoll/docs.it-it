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
ms.openlocfilehash: 5a957a042875b546a18a17422f355b712756e91c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73098166"
---
# <a name="cordebughandletype-enumeration"></a><span data-ttu-id="944b4-102">Enumerazione CorDebugHandleType</span><span class="sxs-lookup"><span data-stu-id="944b4-102">CorDebugHandleType Enumeration</span></span>
<span data-ttu-id="944b4-103">Indica il tipo di handle.</span><span class="sxs-lookup"><span data-stu-id="944b4-103">Indicates the handle type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="944b4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="944b4-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a><span data-ttu-id="944b4-105">Members</span><span class="sxs-lookup"><span data-stu-id="944b4-105">Members</span></span>  
  
|<span data-ttu-id="944b4-106">Member</span><span class="sxs-lookup"><span data-stu-id="944b4-106">Member</span></span>|<span data-ttu-id="944b4-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="944b4-107">Description</span></span>|  
|------------|-----------------|  
|`HANDLE_STRONG`|<span data-ttu-id="944b4-108">Il punto di controllo è sicuro e impedisce a un oggetto di essere recuperato da Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="944b4-108">The handle is strong, which prevents an object from being reclaimed by garbage collection.</span></span>|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|<span data-ttu-id="944b4-109">L'handle è debole, che non impedisce che un oggetto venga recuperato dal Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="944b4-109">The handle is weak, which does not prevent an object from being reclaimed by garbage collection.</span></span><br /><br /> <span data-ttu-id="944b4-110">Quando l'oggetto viene raccolto, l'handle diventa non valido.</span><span class="sxs-lookup"><span data-stu-id="944b4-110">The handle becomes invalid when the object is collected.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="944b4-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="944b4-111">Requirements</span></span>  
 <span data-ttu-id="944b4-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="944b4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="944b4-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="944b4-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="944b4-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="944b4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="944b4-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="944b4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="944b4-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="944b4-116">See also</span></span>

- [<span data-ttu-id="944b4-117">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="944b4-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

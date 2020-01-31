---
title: Enumerazione CorDebugExceptionUnwindCallbackType
ms.date: 03/30/2017
api_name:
- CorDebugExceptionUnwindCallbackType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionUnwindCallbackType
helpviewer_keywords:
- CorDebugExceptionUnwindCallbackType enumeration [.NET Framework debugging]
ms.assetid: 783dce92-8a98-43db-8f78-888d943dd5b2
topic_type:
- apiref
ms.openlocfilehash: e714c41812c8aaccd713115712df05744cc015e3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789390"
---
# <a name="cordebugexceptionunwindcallbacktype-enumeration"></a><span data-ttu-id="9838d-102">Enumerazione CorDebugExceptionUnwindCallbackType</span><span class="sxs-lookup"><span data-stu-id="9838d-102">CorDebugExceptionUnwindCallbackType Enumeration</span></span>
<span data-ttu-id="9838d-103">Indica l'evento segnalato dal callback durante la fase di rimozione.</span><span class="sxs-lookup"><span data-stu-id="9838d-103">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9838d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9838d-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionUnwindCallbackType {  
    DEBUG_EXCEPTION_UNWIND_BEGIN = 1,  
    DEBUG_EXCEPTION_INTERCEPTED  = 2  
} CorDebugExceptionUnwindCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="9838d-105">Membri</span><span class="sxs-lookup"><span data-stu-id="9838d-105">Members</span></span>  
  
|<span data-ttu-id="9838d-106">Member</span><span class="sxs-lookup"><span data-stu-id="9838d-106">Member</span></span>|<span data-ttu-id="9838d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9838d-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_UNWIND_BEGIN`|<span data-ttu-id="9838d-108">Inizio del processo di rimozione.</span><span class="sxs-lookup"><span data-stu-id="9838d-108">The beginning of the unwind process.</span></span>|  
|`DEBUG_EXCEPTION_INTERCEPTED`|<span data-ttu-id="9838d-109">L'eccezione è stata intercettata.</span><span class="sxs-lookup"><span data-stu-id="9838d-109">The exception was intercepted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9838d-110">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="9838d-110">Requirements</span></span>  
 <span data-ttu-id="9838d-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9838d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9838d-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9838d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9838d-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9838d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9838d-114">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9838d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9838d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9838d-115">See also</span></span>

- [<span data-ttu-id="9838d-116">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="9838d-116">Debugging Enumerations</span></span>](debugging-enumerations.md)

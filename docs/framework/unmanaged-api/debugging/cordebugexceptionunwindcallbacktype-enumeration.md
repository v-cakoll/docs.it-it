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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 408e72eeaa1dac83c45488d186425f30c6043280
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786373"
---
# <a name="cordebugexceptionunwindcallbacktype-enumeration"></a><span data-ttu-id="7260c-102">Enumerazione CorDebugExceptionUnwindCallbackType</span><span class="sxs-lookup"><span data-stu-id="7260c-102">CorDebugExceptionUnwindCallbackType Enumeration</span></span>
<span data-ttu-id="7260c-103">Indica l'evento segnalato dal callback durante la fase di rimozione.</span><span class="sxs-lookup"><span data-stu-id="7260c-103">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7260c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7260c-104">Syntax</span></span>  
  
```  
typedef enum CorDebugExceptionUnwindCallbackType {  
    DEBUG_EXCEPTION_UNWIND_BEGIN = 1,  
    DEBUG_EXCEPTION_INTERCEPTED  = 2  
} CorDebugExceptionUnwindCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="7260c-105">Membri</span><span class="sxs-lookup"><span data-stu-id="7260c-105">Members</span></span>  
  
|<span data-ttu-id="7260c-106">Member</span><span class="sxs-lookup"><span data-stu-id="7260c-106">Member</span></span>|<span data-ttu-id="7260c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7260c-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_UNWIND_BEGIN`|<span data-ttu-id="7260c-108">Inizio del processo di rimozione.</span><span class="sxs-lookup"><span data-stu-id="7260c-108">The beginning of the unwind process.</span></span>|  
|`DEBUG_EXCEPTION_INTERCEPTED`|<span data-ttu-id="7260c-109">È stata intercettata l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="7260c-109">The exception was intercepted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7260c-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7260c-110">Requirements</span></span>  
 <span data-ttu-id="7260c-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7260c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7260c-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7260c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7260c-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7260c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7260c-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7260c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7260c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7260c-115">See also</span></span>

- [<span data-ttu-id="7260c-116">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="7260c-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

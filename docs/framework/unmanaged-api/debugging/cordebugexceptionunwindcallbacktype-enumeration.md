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
ms.openlocfilehash: 5004cd293b64436c41caef1c7393d2229d1a6ccf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73098474"
---
# <a name="cordebugexceptionunwindcallbacktype-enumeration"></a><span data-ttu-id="ca1d9-102">Enumerazione CorDebugExceptionUnwindCallbackType</span><span class="sxs-lookup"><span data-stu-id="ca1d9-102">CorDebugExceptionUnwindCallbackType Enumeration</span></span>
<span data-ttu-id="ca1d9-103">Indica l'evento segnalato dal callback durante la fase di rimozione.</span><span class="sxs-lookup"><span data-stu-id="ca1d9-103">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca1d9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ca1d9-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionUnwindCallbackType {  
    DEBUG_EXCEPTION_UNWIND_BEGIN = 1,  
    DEBUG_EXCEPTION_INTERCEPTED  = 2  
} CorDebugExceptionUnwindCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="ca1d9-105">Members</span><span class="sxs-lookup"><span data-stu-id="ca1d9-105">Members</span></span>  
  
|<span data-ttu-id="ca1d9-106">Member</span><span class="sxs-lookup"><span data-stu-id="ca1d9-106">Member</span></span>|<span data-ttu-id="ca1d9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ca1d9-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_UNWIND_BEGIN`|<span data-ttu-id="ca1d9-108">Inizio del processo di rimozione.</span><span class="sxs-lookup"><span data-stu-id="ca1d9-108">The beginning of the unwind process.</span></span>|  
|`DEBUG_EXCEPTION_INTERCEPTED`|<span data-ttu-id="ca1d9-109">L'eccezione è stata intercettata.</span><span class="sxs-lookup"><span data-stu-id="ca1d9-109">The exception was intercepted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ca1d9-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ca1d9-110">Requirements</span></span>  
 <span data-ttu-id="ca1d9-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca1d9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca1d9-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ca1d9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca1d9-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca1d9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca1d9-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca1d9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca1d9-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca1d9-115">See also</span></span>

- [<span data-ttu-id="ca1d9-116">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="ca1d9-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

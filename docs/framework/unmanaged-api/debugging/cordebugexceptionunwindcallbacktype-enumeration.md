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
ms.openlocfilehash: 7fe2fcf10b517f4eb7b1c7e87142afb386821246
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404111"
---
# <a name="cordebugexceptionunwindcallbacktype-enumeration"></a><span data-ttu-id="58b6b-102">Enumerazione CorDebugExceptionUnwindCallbackType</span><span class="sxs-lookup"><span data-stu-id="58b6b-102">CorDebugExceptionUnwindCallbackType Enumeration</span></span>
<span data-ttu-id="58b6b-103">Indica l'evento segnalato dal callback durante la fase di rimozione.</span><span class="sxs-lookup"><span data-stu-id="58b6b-103">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58b6b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="58b6b-104">Syntax</span></span>  
  
```  
typedef enum CorDebugExceptionUnwindCallbackType {  
    DEBUG_EXCEPTION_UNWIND_BEGIN = 1,  
    DEBUG_EXCEPTION_INTERCEPTED  = 2  
} CorDebugExceptionUnwindCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="58b6b-105">Membri</span><span class="sxs-lookup"><span data-stu-id="58b6b-105">Members</span></span>  
  
|<span data-ttu-id="58b6b-106">Membro</span><span class="sxs-lookup"><span data-stu-id="58b6b-106">Member</span></span>|<span data-ttu-id="58b6b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58b6b-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_UNWIND_BEGIN`|<span data-ttu-id="58b6b-108">Inizio del processo di rimozione.</span><span class="sxs-lookup"><span data-stu-id="58b6b-108">The beginning of the unwind process.</span></span>|  
|`DEBUG_EXCEPTION_INTERCEPTED`|<span data-ttu-id="58b6b-109">L'eccezione è stata intercettata.</span><span class="sxs-lookup"><span data-stu-id="58b6b-109">The exception was intercepted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="58b6b-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="58b6b-110">Requirements</span></span>  
 <span data-ttu-id="58b6b-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58b6b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58b6b-112">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="58b6b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="58b6b-113">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="58b6b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58b6b-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58b6b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58b6b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58b6b-115">See Also</span></span>  
 [<span data-ttu-id="58b6b-116">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="58b6b-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

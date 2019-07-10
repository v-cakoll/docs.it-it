---
title: Enumerazione CorDebugExceptionCallbackType
ms.date: 03/30/2017
api_name:
- CorDebugExceptionCallbackType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionCallbackType
helpviewer_keywords:
- CorDebugExceptionCallbackType enumeration [.NET Framework debugging]
ms.assetid: 4d946ad4-3c19-42cb-bec9-8633325ba769
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b712ee0bb8e67f448b7ea2bee3c092367181abad
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740219"
---
# <a name="cordebugexceptioncallbacktype-enumeration"></a><span data-ttu-id="9be8f-102">Enumerazione CorDebugExceptionCallbackType</span><span class="sxs-lookup"><span data-stu-id="9be8f-102">CorDebugExceptionCallbackType Enumeration</span></span>
<span data-ttu-id="9be8f-103">Indica il tipo di callback che viene eseguita da un [ICorDebugManagedCallback2::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) evento.</span><span class="sxs-lookup"><span data-stu-id="9be8f-103">Indicates the type of callback that is made from an [ICorDebugManagedCallback2::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9be8f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9be8f-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionCallbackType {  
    DEBUG_EXCEPTION_FIRST_CHANCE         = 1,  
    DEBUG_EXCEPTION_USER_FIRST_CHANCE    = 2,  
    DEBUG_EXCEPTION_CATCH_HANDLER_FOUND  = 3,  
    DEBUG_EXCEPTION_UNHANDLED            = 4  
} CorDebugExceptionCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="9be8f-105">Membri</span><span class="sxs-lookup"><span data-stu-id="9be8f-105">Members</span></span>  
  
|<span data-ttu-id="9be8f-106">Member</span><span class="sxs-lookup"><span data-stu-id="9be8f-106">Member</span></span>|<span data-ttu-id="9be8f-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9be8f-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="9be8f-108">È stata generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="9be8f-108">An exception was thrown.</span></span>|  
|`DEBUG_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="9be8f-109">Il processo di chiusura eccezione immesso il codice utente.</span><span class="sxs-lookup"><span data-stu-id="9be8f-109">The exception windup process entered user code.</span></span>|  
|`DEBUG_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="9be8f-110">Il processo di chiusura di eccezione trovato un `catch` blocco nel codice utente.</span><span class="sxs-lookup"><span data-stu-id="9be8f-110">The exception windup process found a `catch` block in user code.</span></span>|  
|`DEBUG_EXCEPTION_UNHANDLED`|<span data-ttu-id="9be8f-111">L'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="9be8f-111">The exception was not handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9be8f-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9be8f-112">Requirements</span></span>  
 <span data-ttu-id="9be8f-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9be8f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9be8f-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9be8f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9be8f-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9be8f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9be8f-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9be8f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9be8f-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9be8f-117">See also</span></span>

- [<span data-ttu-id="9be8f-118">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="9be8f-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

---
title: Enumerazione CorDebugDebugEventKind
ms.date: 03/30/2017
api_name:
- CorDebugDebugEventKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6075a6cd-97e6-4472-a090-0dd14860d1f3
topic_type:
- apiref
ms.openlocfilehash: de4ac1f39ea9cfb4b616bd4e2c85e5de530dbb0b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132222"
---
# <a name="cordebugdebugeventkind-enumeration"></a><span data-ttu-id="7a416-102">Enumerazione CorDebugDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="7a416-102">CorDebugDebugEventKind Enumeration</span></span>
<span data-ttu-id="7a416-103">Indica il tipo di evento le cui informazioni sono decodificate dal metodo [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7a416-103">Indicates the type of event whose information is decoded by the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a416-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7a416-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugDebugEventKind {  
    DEBUG_EVENT_KIND_MODULE_LOADED                          = 1,  
    DEBUG_EVENT_KIND_MODULE_UNLOADED                        = 2,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE         = 3,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE    = 4,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND  = 5,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED            = 6  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="7a416-105">Members</span><span class="sxs-lookup"><span data-stu-id="7a416-105">Members</span></span>  
  
|<span data-ttu-id="7a416-106">Member</span><span class="sxs-lookup"><span data-stu-id="7a416-106">Member</span></span>|<span data-ttu-id="7a416-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7a416-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EVENT_KIND_MODULE_LOADED`|<span data-ttu-id="7a416-108">Evento di caricamento del modulo.</span><span class="sxs-lookup"><span data-stu-id="7a416-108">A module load event.</span></span>|  
|`DEBUG_EVENT_KIND_MODULE_UNLOADED`|<span data-ttu-id="7a416-109">Evento di scaricamento del modulo.</span><span class="sxs-lookup"><span data-stu-id="7a416-109">A module unload event.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="7a416-110">Eccezione first-chance.</span><span class="sxs-lookup"><span data-stu-id="7a416-110">A first-chance exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="7a416-111">Eccezione utente first-chance.</span><span class="sxs-lookup"><span data-stu-id="7a416-111">A first-chance user exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="7a416-112">Eccezione per la quale esiste un gestore `catch`.</span><span class="sxs-lookup"><span data-stu-id="7a416-112">An exception for which a `catch` handler exists.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED`|<span data-ttu-id="7a416-113">Eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="7a416-113">An unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a416-114">Note</span><span class="sxs-lookup"><span data-stu-id="7a416-114">Remarks</span></span>  
 <span data-ttu-id="7a416-115">Un membro dell'enumerazione `CorDebugDebugEventKind` viene restituito chiamando il metodo [ICorDebugDebugEvent:: GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7a416-115">A member of the `CorDebugDebugEventKind` enumeration is returned by calling the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7a416-116">Questa enumerazione è progettata per l'uso solo in scenari di debug di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="7a416-116">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a416-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7a416-117">Requirements</span></span>  
 <span data-ttu-id="7a416-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a416-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a416-119">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7a416-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7a416-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a416-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a416-121">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a416-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a416-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a416-122">See also</span></span>

- [<span data-ttu-id="7a416-123">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="7a416-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

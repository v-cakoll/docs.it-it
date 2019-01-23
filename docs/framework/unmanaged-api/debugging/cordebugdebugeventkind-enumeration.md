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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a45929c3eef5e9127e89dd88346c6207f3f1bc65
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559492"
---
# <a name="cordebugdebugeventkind-enumeration"></a><span data-ttu-id="40a5d-102">Enumerazione CorDebugDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="40a5d-102">CorDebugDebugEventKind Enumeration</span></span>
<span data-ttu-id="40a5d-103">Indica il tipo di evento le cui informazioni sono decodificate dal [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="40a5d-103">Indicates the type of event whose information is decoded by the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40a5d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="40a5d-104">Syntax</span></span>  
  
```  
typedef enum CorDebugDebugEventKind {  
    DEBUG_EVENT_KIND_MODULE_LOADED                          = 1,  
    DEBUG_EVENT_KIND_MODULE_UNLOADED                        = 2,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE         = 3,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE    = 4,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND  = 5,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED            = 6  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="40a5d-105">Membri</span><span class="sxs-lookup"><span data-stu-id="40a5d-105">Members</span></span>  
  
|<span data-ttu-id="40a5d-106">Membro</span><span class="sxs-lookup"><span data-stu-id="40a5d-106">Member</span></span>|<span data-ttu-id="40a5d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="40a5d-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EVENT_KIND_MODULE_LOADED`|<span data-ttu-id="40a5d-108">Evento di caricamento del modulo.</span><span class="sxs-lookup"><span data-stu-id="40a5d-108">A module load event.</span></span>|  
|`DEBUG_EVENT_KIND_MODULE_UNLOADED`|<span data-ttu-id="40a5d-109">Evento di scaricamento del modulo.</span><span class="sxs-lookup"><span data-stu-id="40a5d-109">A module unload event.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="40a5d-110">Eccezione first-chance.</span><span class="sxs-lookup"><span data-stu-id="40a5d-110">A first-chance exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="40a5d-111">Eccezione utente first-chance.</span><span class="sxs-lookup"><span data-stu-id="40a5d-111">A first-chance user exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="40a5d-112">Eccezione per la quale esiste un gestore `catch`.</span><span class="sxs-lookup"><span data-stu-id="40a5d-112">An exception for which a `catch` handler exists.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED`|<span data-ttu-id="40a5d-113">Eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="40a5d-113">An unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40a5d-114">Note</span><span class="sxs-lookup"><span data-stu-id="40a5d-114">Remarks</span></span>  
 <span data-ttu-id="40a5d-115">Un membro del `CorDebugDebugEventKind` enumerazione viene restituita chiamando il [icordebugdebugevent:: Geteventkind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="40a5d-115">A member of the `CorDebugDebugEventKind` enumeration is returned by calling the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="40a5d-116">Questa enumerazione è progettata per l'uso solo in scenari di debug di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="40a5d-116">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40a5d-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="40a5d-117">Requirements</span></span>  
 <span data-ttu-id="40a5d-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40a5d-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40a5d-119">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="40a5d-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="40a5d-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40a5d-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40a5d-121">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40a5d-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40a5d-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40a5d-122">See also</span></span>
- [<span data-ttu-id="40a5d-123">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="40a5d-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

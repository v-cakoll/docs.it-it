---
title: Enumerazione CorDebugDecodeEventFlagsWindows
ms.date: 03/30/2017
api_name:
- CorDebugDecodeEventFlagsWindows
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: aa6cf962-30ae-4cfd-8895-826deeb46a54
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d4e006a03db5b16de93dfd07ec7b964db4bfc1d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207734"
---
# <a name="cordebugdecodeeventflagswindows-enumeration"></a><span data-ttu-id="ed84f-102">Enumerazione CorDebugDecodeEventFlagsWindows</span><span class="sxs-lookup"><span data-stu-id="ed84f-102">CorDebugDecodeEventFlagsWindows Enumeration</span></span>
<span data-ttu-id="ed84f-103">Fornisce altre informazioni sugli eventi di debug nella piattaforma Windows.</span><span class="sxs-lookup"><span data-stu-id="ed84f-103">Provides additional information about debug events on the Windows platform.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed84f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ed84f-104">Syntax</span></span>  
  
```  
typedef enum CorDebugDecodeEventFlagsWindows {  
    IS_FIRST_CHANCE = 1,  
} CorDebugDecodeEventFlagsWindows;  
```  
  
## <a name="members"></a><span data-ttu-id="ed84f-105">Membri</span><span class="sxs-lookup"><span data-stu-id="ed84f-105">Members</span></span>  
  
|<span data-ttu-id="ed84f-106">Member</span><span class="sxs-lookup"><span data-stu-id="ed84f-106">Member</span></span>|<span data-ttu-id="ed84f-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ed84f-107">Description</span></span>|  
|------------|-----------------|  
|`IS_FIRST_CHANCE`|<span data-ttu-id="ed84f-108">Indica che l'evento di debug è un'eccezione first-chance.</span><span class="sxs-lookup"><span data-stu-id="ed84f-108">Indicates that the debug event is a first-chance exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed84f-109">Note</span><span class="sxs-lookup"><span data-stu-id="ed84f-109">Remarks</span></span>  
 <span data-ttu-id="ed84f-110">Il [ICorDebugProcess6::DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) metodo include un `dwFlags` parametro che fornisce informazioni aggiuntive su un evento di debug e il cui valore è dipendente dall'architettura di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ed84f-110">The [ICorDebugProcess6::DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method includes a `dwFlags` parameter that provides additional information about a debug event and whose value is dependent on the target architecture.</span></span> <span data-ttu-id="ed84f-111">L'enumerazione `CorDebugDecodeEventFlagsWindows` può essere usata con gli eventi di debug nella piattaforma Windows.</span><span class="sxs-lookup"><span data-stu-id="ed84f-111">The `CorDebugDecodeEventFlagsWindows` enumeration can be used with debug events on the Windows platform.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ed84f-112">Questa enumerazione è progettata per l'uso solo in scenari di debug di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="ed84f-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed84f-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ed84f-113">Requirements</span></span>  
 <span data-ttu-id="ed84f-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed84f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed84f-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ed84f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ed84f-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed84f-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ed84f-117">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ed84f-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ed84f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed84f-118">See also</span></span>

- [<span data-ttu-id="ed84f-119">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="ed84f-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

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
ms.openlocfilehash: ec23e0f272852088987fcc74767d3645778eab45
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955688"
---
# <a name="cordebugdecodeeventflagswindows-enumeration"></a><span data-ttu-id="ef352-102">Enumerazione CorDebugDecodeEventFlagsWindows</span><span class="sxs-lookup"><span data-stu-id="ef352-102">CorDebugDecodeEventFlagsWindows Enumeration</span></span>
<span data-ttu-id="ef352-103">Fornisce altre informazioni sugli eventi di debug nella piattaforma Windows.</span><span class="sxs-lookup"><span data-stu-id="ef352-103">Provides additional information about debug events on the Windows platform.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef352-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ef352-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugDecodeEventFlagsWindows {  
    IS_FIRST_CHANCE = 1,  
} CorDebugDecodeEventFlagsWindows;  
```  
  
## <a name="members"></a><span data-ttu-id="ef352-105">Members</span><span class="sxs-lookup"><span data-stu-id="ef352-105">Members</span></span>  
  
|<span data-ttu-id="ef352-106">Member</span><span class="sxs-lookup"><span data-stu-id="ef352-106">Member</span></span>|<span data-ttu-id="ef352-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ef352-107">Description</span></span>|  
|------------|-----------------|  
|`IS_FIRST_CHANCE`|<span data-ttu-id="ef352-108">Indica che l'evento di debug è un'eccezione first-chance.</span><span class="sxs-lookup"><span data-stu-id="ef352-108">Indicates that the debug event is a first-chance exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef352-109">Note</span><span class="sxs-lookup"><span data-stu-id="ef352-109">Remarks</span></span>  
 <span data-ttu-id="ef352-110">Il metodo [Metodo icordebugprocess6::D ecodeevent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) include un `dwFlags` parametro che fornisce informazioni aggiuntive su un evento di debug e il cui valore dipende dall'architettura di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ef352-110">The [ICorDebugProcess6::DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method includes a `dwFlags` parameter that provides additional information about a debug event and whose value is dependent on the target architecture.</span></span> <span data-ttu-id="ef352-111">L'enumerazione `CorDebugDecodeEventFlagsWindows` può essere usata con gli eventi di debug nella piattaforma Windows.</span><span class="sxs-lookup"><span data-stu-id="ef352-111">The `CorDebugDecodeEventFlagsWindows` enumeration can be used with debug events on the Windows platform.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ef352-112">Questa enumerazione è progettata per l'uso solo in scenari di debug di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="ef352-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef352-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ef352-113">Requirements</span></span>  
 <span data-ttu-id="ef352-114">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef352-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef352-115">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="ef352-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ef352-116">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef352-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef352-117">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef352-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef352-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef352-118">See also</span></span>

- [<span data-ttu-id="ef352-119">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="ef352-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

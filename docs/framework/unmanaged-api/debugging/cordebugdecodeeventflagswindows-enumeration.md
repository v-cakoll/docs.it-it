---
title: Enumerazione CorDebugDecodeEventFlagsWindows
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugDecodeEventFlagsWindows
api_location: mscordbi.dll
api_type: COM
ms.assetid: aa6cf962-30ae-4cfd-8895-826deeb46a54
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: facde76ec24d90795de7dfb70bfe5772a6f21531
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugdecodeeventflagswindows-enumeration"></a><span data-ttu-id="bb43d-102">Enumerazione CorDebugDecodeEventFlagsWindows</span><span class="sxs-lookup"><span data-stu-id="bb43d-102">CorDebugDecodeEventFlagsWindows Enumeration</span></span>
<span data-ttu-id="bb43d-103">Fornisce altre informazioni sugli eventi di debug nella piattaforma Windows.</span><span class="sxs-lookup"><span data-stu-id="bb43d-103">Provides additional information about debug events on the Windows platform.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb43d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bb43d-104">Syntax</span></span>  
  
```  
typedef enum CorDebugDecodeEventFlagsWindows {  
    IS_FIRST_CHANCE = 1,  
} CorDebugDecodeEventFlagsWindows;  
```  
  
## <a name="members"></a><span data-ttu-id="bb43d-105">Membri</span><span class="sxs-lookup"><span data-stu-id="bb43d-105">Members</span></span>  
  
|<span data-ttu-id="bb43d-106">Membro</span><span class="sxs-lookup"><span data-stu-id="bb43d-106">Member</span></span>|<span data-ttu-id="bb43d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb43d-107">Description</span></span>|  
|------------|-----------------|  
|`IS_FIRST_CHANCE`|<span data-ttu-id="bb43d-108">Indica che l'evento di debug è un'eccezione first-chance.</span><span class="sxs-lookup"><span data-stu-id="bb43d-108">Indicates that the debug event is a first-chance exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb43d-109">Note</span><span class="sxs-lookup"><span data-stu-id="bb43d-109">Remarks</span></span>  
 <span data-ttu-id="bb43d-110">Il [icordebugprocess6:: Decodeevent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) metodo include un `dwFlags` parametro che fornisce informazioni aggiuntive su un evento di debug e il cui valore è dipendente dall'architettura di destinazione.</span><span class="sxs-lookup"><span data-stu-id="bb43d-110">The [ICorDebugProcess6::DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method includes a `dwFlags` parameter that provides additional information about a debug event and whose value is dependent on the target architecture.</span></span> <span data-ttu-id="bb43d-111">L'enumerazione `CorDebugDecodeEventFlagsWindows` può essere usata con gli eventi di debug nella piattaforma Windows.</span><span class="sxs-lookup"><span data-stu-id="bb43d-111">The `CorDebugDecodeEventFlagsWindows` enumeration can be used with debug events on the Windows platform.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb43d-112">Questa enumerazione è progettata per l'uso solo in scenari di debug di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="bb43d-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb43d-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bb43d-113">Requirements</span></span>  
 <span data-ttu-id="bb43d-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb43d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb43d-115">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="bb43d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb43d-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb43d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb43d-117">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb43d-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb43d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb43d-118">See Also</span></span>  
 [<span data-ttu-id="bb43d-119">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="bb43d-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

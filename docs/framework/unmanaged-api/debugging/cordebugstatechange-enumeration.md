---
title: Enumerazione CorDebugStateChange
ms.date: 03/30/2017
api_name:
- CorDebugStateChange
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 1d4424ab-5143-4e50-a84a-ceeb4ddf3bba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 841108457293e3377ee87f9c7d7c6898340e51b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404346"
---
# <a name="cordebugstatechange-enumeration"></a><span data-ttu-id="abad5-102">Enumerazione CorDebugStateChange</span><span class="sxs-lookup"><span data-stu-id="abad5-102">CorDebugStateChange Enumeration</span></span>
<span data-ttu-id="abad5-103">Descrive la quantità di dati memorizzati nella cache da rimuovere in base alle modifiche apportate al processo.</span><span class="sxs-lookup"><span data-stu-id="abad5-103">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abad5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="abad5-104">Syntax</span></span>  
  
```  
typedef enum CorDebugStateChange  
{  
    PROCESS_RUNNING = 0x0000001,   
    FLUSH_ALL       = 0x0000002,   
} CorDebugStateChange;  
```  
  
## <a name="members"></a><span data-ttu-id="abad5-105">Membri</span><span class="sxs-lookup"><span data-stu-id="abad5-105">Members</span></span>  
  
|<span data-ttu-id="abad5-106">Membro</span><span class="sxs-lookup"><span data-stu-id="abad5-106">Member</span></span>|<span data-ttu-id="abad5-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="abad5-107">Description</span></span>|  
|------------|-----------------|  
|`PROCESS_RUNNING`|<span data-ttu-id="abad5-108">Il processo ha raggiunto un nuovo stato di memoria tramite l'esecuzione diretta.</span><span class="sxs-lookup"><span data-stu-id="abad5-108">The process reached a new memory state via forward execution.</span></span>|  
|`SET_CONTEXT_FLAG_UNWIND_FRAME`|<span data-ttu-id="abad5-109">La memoria del processo può essere diversa in modo arbitrario rispetto allo stato precedente.</span><span class="sxs-lookup"><span data-stu-id="abad5-109">The process' memory may be arbitrarily different than it was previously.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="abad5-110">Note</span><span class="sxs-lookup"><span data-stu-id="abad5-110">Remarks</span></span>  
 <span data-ttu-id="abad5-111">Membro di `CorDebugStateChange` enumerazione viene fornita come argomento quando il debugger chiama il [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) (metodo)</span><span class="sxs-lookup"><span data-stu-id="abad5-111">A member of the `CorDebugStateChange` enumeration is provided as an argument when the debugger calls the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) method</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="abad5-112">Questa enumerazione è progettata per l'uso solo in scenari di debug di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="abad5-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abad5-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="abad5-113">Requirements</span></span>  
 <span data-ttu-id="abad5-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="abad5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abad5-115">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="abad5-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="abad5-116">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="abad5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="abad5-117">**Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abad5-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abad5-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="abad5-118">See Also</span></span>  
 [<span data-ttu-id="abad5-119">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="abad5-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="abad5-120">Debug</span><span class="sxs-lookup"><span data-stu-id="abad5-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

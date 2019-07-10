---
title: Enumerazione CorDebugStateChange
ms.date: 02/07/2019
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
ms.openlocfilehash: 676489880cb30ca540cb78d70797dbf4eedf7395
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739592"
---
# <a name="cordebugstatechange-enumeration"></a><span data-ttu-id="57fd3-102">Enumerazione CorDebugStateChange</span><span class="sxs-lookup"><span data-stu-id="57fd3-102">CorDebugStateChange Enumeration</span></span>

<span data-ttu-id="57fd3-103">Descrive la quantità di dati memorizzati nella cache da rimuovere in base alle modifiche apportate al processo.</span><span class="sxs-lookup"><span data-stu-id="57fd3-103">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>

## <a name="syntax"></a><span data-ttu-id="57fd3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="57fd3-104">Syntax</span></span>

```cpp
typedef enum CorDebugStateChange
{
    PROCESS_RUNNING = 0x0000001,
    FLUSH_ALL       = 0x0000002,
} CorDebugStateChange;
```

## <a name="members"></a><span data-ttu-id="57fd3-105">Membri</span><span class="sxs-lookup"><span data-stu-id="57fd3-105">Members</span></span>

| <span data-ttu-id="57fd3-106">Member</span><span class="sxs-lookup"><span data-stu-id="57fd3-106">Member</span></span>            | <span data-ttu-id="57fd3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="57fd3-107">Description</span></span>                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| `PROCESS_RUNNING` | <span data-ttu-id="57fd3-108">Il processo ha raggiunto un nuovo stato di memoria tramite l'esecuzione diretta.</span><span class="sxs-lookup"><span data-stu-id="57fd3-108">The process reached a new memory state via forward execution.</span></span>            |
| `FLUSH_ALL`       | <span data-ttu-id="57fd3-109">La memoria del processo può essere diversa in modo arbitrario rispetto allo stato precedente.</span><span class="sxs-lookup"><span data-stu-id="57fd3-109">The process' memory may be arbitrarily different than it was previously.</span></span> |

## <a name="remarks"></a><span data-ttu-id="57fd3-110">Note</span><span class="sxs-lookup"><span data-stu-id="57fd3-110">Remarks</span></span>

 <span data-ttu-id="57fd3-111">Un membro del `CorDebugStateChange` enumerazione viene fornita come argomento quando il debugger chiama il `ProcessStateChanged` metodo mediante [ICorDebugProcess4::ProcessStateChanged](icordebugprocess4-processstatechanged-method.md) o [ICorDebugProcess6:: ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)</span><span class="sxs-lookup"><span data-stu-id="57fd3-111">A member of the `CorDebugStateChange` enumeration is provided as an argument when the debugger calls the `ProcessStateChanged` method either with [ICorDebugProcess4::ProcessStateChanged](icordebugprocess4-processstatechanged-method.md) or [ICorDebugProcess6::ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)</span></span>

## <a name="requirements"></a><span data-ttu-id="57fd3-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="57fd3-112">Requirements</span></span>

 <span data-ttu-id="57fd3-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57fd3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="57fd3-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="57fd3-114">**Header:** CorDebug.idl, CorDebug.h</span></span>

 <span data-ttu-id="57fd3-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57fd3-115">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="57fd3-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57fd3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="57fd3-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57fd3-117">See also</span></span>

- [<span data-ttu-id="57fd3-118">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="57fd3-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="57fd3-119">Debug</span><span class="sxs-lookup"><span data-stu-id="57fd3-119">Debugging</span></span>](index.md)

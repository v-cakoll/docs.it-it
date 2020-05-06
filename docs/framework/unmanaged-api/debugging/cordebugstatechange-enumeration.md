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
ms.openlocfilehash: d94422d25da91cd2a6653a95cbd852c3930a151a
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795690"
---
# <a name="cordebugstatechange-enumeration"></a><span data-ttu-id="7a976-102">Enumerazione CorDebugStateChange</span><span class="sxs-lookup"><span data-stu-id="7a976-102">CorDebugStateChange Enumeration</span></span>

<span data-ttu-id="7a976-103">Descrive la quantità di dati memorizzati nella cache da rimuovere in base alle modifiche apportate al processo.</span><span class="sxs-lookup"><span data-stu-id="7a976-103">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>

## <a name="syntax"></a><span data-ttu-id="7a976-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7a976-104">Syntax</span></span>

```cpp
typedef enum CorDebugStateChange
{
    PROCESS_RUNNING = 0x0000001,
    FLUSH_ALL       = 0x0000002,
} CorDebugStateChange;
```

## <a name="members"></a><span data-ttu-id="7a976-105">Members</span><span class="sxs-lookup"><span data-stu-id="7a976-105">Members</span></span>

| <span data-ttu-id="7a976-106">Membro</span><span class="sxs-lookup"><span data-stu-id="7a976-106">Member</span></span>            | <span data-ttu-id="7a976-107">Description</span><span class="sxs-lookup"><span data-stu-id="7a976-107">Description</span></span>                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| `PROCESS_RUNNING` | <span data-ttu-id="7a976-108">Il processo ha raggiunto un nuovo stato di memoria tramite l'esecuzione diretta.</span><span class="sxs-lookup"><span data-stu-id="7a976-108">The process reached a new memory state via forward execution.</span></span>            |
| `FLUSH_ALL`       | <span data-ttu-id="7a976-109">La memoria del processo può essere diversa in modo arbitrario rispetto allo stato precedente.</span><span class="sxs-lookup"><span data-stu-id="7a976-109">The process' memory may be arbitrarily different than it was previously.</span></span> |

## <a name="remarks"></a><span data-ttu-id="7a976-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="7a976-110">Remarks</span></span>

 <span data-ttu-id="7a976-111">`CorDebugStateChange` Un membro dell'enumerazione viene fornito come argomento quando il debugger chiama `ProcessStateChanged` il metodo con [ICorDebugProcess4::P rocessStateChanged](icordebugprocess4-processstatechanged-method.md) o [Metodo icordebugprocess6::P rocessstatechanged](icordebugprocess6-processstatechanged-method.md)</span><span class="sxs-lookup"><span data-stu-id="7a976-111">A member of the `CorDebugStateChange` enumeration is provided as an argument when the debugger calls the `ProcessStateChanged` method either with [ICorDebugProcess4::ProcessStateChanged](icordebugprocess4-processstatechanged-method.md) or [ICorDebugProcess6::ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)</span></span>

## <a name="requirements"></a><span data-ttu-id="7a976-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7a976-112">Requirements</span></span>

 <span data-ttu-id="7a976-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a976-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="7a976-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7a976-114">**Header:** CorDebug.idl, CorDebug.h</span></span>

 <span data-ttu-id="7a976-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a976-115">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="7a976-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a976-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="7a976-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a976-117">See also</span></span>

- [<span data-ttu-id="7a976-118">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="7a976-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="7a976-119">Debug</span><span class="sxs-lookup"><span data-stu-id="7a976-119">Debugging</span></span>](index.md)

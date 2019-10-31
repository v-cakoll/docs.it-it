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
ms.openlocfilehash: 239e3a82df0e6010278669f9f429bfad0d163319
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133715"
---
# <a name="cordebugstatechange-enumeration"></a><span data-ttu-id="b1f18-102">Enumerazione CorDebugStateChange</span><span class="sxs-lookup"><span data-stu-id="b1f18-102">CorDebugStateChange Enumeration</span></span>

<span data-ttu-id="b1f18-103">Descrive la quantità di dati memorizzati nella cache da rimuovere in base alle modifiche apportate al processo.</span><span class="sxs-lookup"><span data-stu-id="b1f18-103">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>

## <a name="syntax"></a><span data-ttu-id="b1f18-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b1f18-104">Syntax</span></span>

```cpp
typedef enum CorDebugStateChange
{
    PROCESS_RUNNING = 0x0000001,
    FLUSH_ALL       = 0x0000002,
} CorDebugStateChange;
```

## <a name="members"></a><span data-ttu-id="b1f18-105">Members</span><span class="sxs-lookup"><span data-stu-id="b1f18-105">Members</span></span>

| <span data-ttu-id="b1f18-106">Member</span><span class="sxs-lookup"><span data-stu-id="b1f18-106">Member</span></span>            | <span data-ttu-id="b1f18-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b1f18-107">Description</span></span>                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| `PROCESS_RUNNING` | <span data-ttu-id="b1f18-108">Il processo ha raggiunto un nuovo stato di memoria tramite l'esecuzione diretta.</span><span class="sxs-lookup"><span data-stu-id="b1f18-108">The process reached a new memory state via forward execution.</span></span>            |
| `FLUSH_ALL`       | <span data-ttu-id="b1f18-109">La memoria del processo può essere diversa in modo arbitrario rispetto allo stato precedente.</span><span class="sxs-lookup"><span data-stu-id="b1f18-109">The process' memory may be arbitrarily different than it was previously.</span></span> |

## <a name="remarks"></a><span data-ttu-id="b1f18-110">Note</span><span class="sxs-lookup"><span data-stu-id="b1f18-110">Remarks</span></span>

 <span data-ttu-id="b1f18-111">Un membro dell'enumerazione `CorDebugStateChange` viene fornito come argomento quando il debugger chiama il metodo `ProcessStateChanged` con [ICorDebugProcess4::P rocessstatechanged](icordebugprocess4-processstatechanged-method.md) o [Metodo icordebugprocess6::P rocessstatechanged](icordebugprocess6-processstatechanged-method.md)</span><span class="sxs-lookup"><span data-stu-id="b1f18-111">A member of the `CorDebugStateChange` enumeration is provided as an argument when the debugger calls the `ProcessStateChanged` method either with [ICorDebugProcess4::ProcessStateChanged](icordebugprocess4-processstatechanged-method.md) or [ICorDebugProcess6::ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)</span></span>

## <a name="requirements"></a><span data-ttu-id="b1f18-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b1f18-112">Requirements</span></span>

 <span data-ttu-id="b1f18-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1f18-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="b1f18-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b1f18-114">**Header:** CorDebug.idl, CorDebug.h</span></span>

 <span data-ttu-id="b1f18-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1f18-115">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="b1f18-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1f18-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b1f18-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1f18-117">See also</span></span>

- [<span data-ttu-id="b1f18-118">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="b1f18-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="b1f18-119">Debug</span><span class="sxs-lookup"><span data-stu-id="b1f18-119">Debugging</span></span>](index.md)

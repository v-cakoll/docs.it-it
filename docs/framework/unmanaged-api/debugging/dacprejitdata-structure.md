---
title: Struttura DacpReJitData
ms.date: 02/01/2019
api.name:
- DacpReJitData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpReJitData Structure
helpviewer.keywords:
- DacpReJitData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 46031f29da6916eeaeea863ebef6924a720d7155
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793820"
---
# <a name="dacprejitdata-structure"></a><span data-ttu-id="fd6be-102">Struttura DacpReJitData</span><span class="sxs-lookup"><span data-stu-id="fd6be-102">DacpReJitData Structure</span></span>

<span data-ttu-id="fd6be-103">Definisce le informazioni di base su un metodo instrumentato fornito dal profiler.</span><span class="sxs-lookup"><span data-stu-id="fd6be-103">Defines the basic information about a given profiler-instrumented method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="fd6be-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fd6be-104">Syntax</span></span>

```cpp
struct MSLAYOUT DacpReJitData
{
    enum Flags
    {
        kUnknown,
        kRequested,
        kActive,
        kReverted,
    };

    CLRDATA_ADDRESS                 rejitID;
    Flags                           flags;
    CLRDATA_ADDRESS                 NativeCodeAddr;
};
```

## <a name="members"></a><span data-ttu-id="fd6be-105">Membri</span><span class="sxs-lookup"><span data-stu-id="fd6be-105">Members</span></span>

| <span data-ttu-id="fd6be-106">Member</span><span class="sxs-lookup"><span data-stu-id="fd6be-106">Member</span></span>           | <span data-ttu-id="fd6be-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fd6be-107">Description</span></span>                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| `rejitID`        | <span data-ttu-id="fd6be-108">Numero di revisione ReJit per un metodo.</span><span class="sxs-lookup"><span data-stu-id="fd6be-108">The ReJit revision number for a method.</span></span>                                                          |
| `flags`          | <span data-ttu-id="fd6be-109">Flag che indica lo stato corrente della strumentazione ReJit del metodo per la versione specificata.</span><span class="sxs-lookup"><span data-stu-id="fd6be-109">A flag indicating the current state of the method's ReJit instrumentation for the given version.</span></span> |
| `NativeCodeAddr` | <span data-ttu-id="fd6be-110">Indirizzo di base dell'implementazione di rejitted del metodo.</span><span class="sxs-lookup"><span data-stu-id="fd6be-110">The base address of the method's rejitted implementation.</span></span>                                         |

## <a name="remarks"></a><span data-ttu-id="fd6be-111">Note</span><span class="sxs-lookup"><span data-stu-id="fd6be-111">Remarks</span></span>

<span data-ttu-id="fd6be-112">Questa struttura si trova all'interno del runtime e non viene esposta tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="fd6be-112">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="fd6be-113">Per usarlo, definire la struttura come specificato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="fd6be-113">To use it, define the structure as specified above.</span></span> <span data-ttu-id="fd6be-114">Se non si usano i compilatori Microsoft, è necessario definire anche la struttura usando `ms_struct` la compressione.</span><span class="sxs-lookup"><span data-stu-id="fd6be-114">The structure must also be defined using `ms_struct` packing if not using the Microsoft compilers.</span></span>

## <a name="requirements"></a><span data-ttu-id="fd6be-115">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="fd6be-115">Requirements</span></span>
<span data-ttu-id="fd6be-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd6be-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="fd6be-117">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="fd6be-117">**Header:** None</span></span>  
<span data-ttu-id="fd6be-118">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="fd6be-118">**Library:** None</span></span>  
<span data-ttu-id="fd6be-119">**Versioni .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fd6be-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="fd6be-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd6be-120">See also</span></span>

- [<span data-ttu-id="fd6be-121">Debug</span><span class="sxs-lookup"><span data-stu-id="fd6be-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="fd6be-122">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="fd6be-122">Debugging Structures</span></span>](debugging-structures.md)

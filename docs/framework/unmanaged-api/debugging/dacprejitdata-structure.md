---
title: DacpReJitData Structure
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
ms.openlocfilehash: a2850add9acb2f7c5297ac6956e349c9277be291
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122798"
---
# <a name="dacprejitdata-structure"></a><span data-ttu-id="a972d-102">DacpReJitData Structure</span><span class="sxs-lookup"><span data-stu-id="a972d-102">DacpReJitData Structure</span></span>

<span data-ttu-id="a972d-103">Definisce le informazioni di base per un determinato metodo instrumentato del profiler.</span><span class="sxs-lookup"><span data-stu-id="a972d-103">Defines the basic information about a given profiler-instrumented method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="a972d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a972d-104">Syntax</span></span>

```
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

## <a name="members"></a><span data-ttu-id="a972d-105">Membri</span><span class="sxs-lookup"><span data-stu-id="a972d-105">Members</span></span>

| <span data-ttu-id="a972d-106">Member</span><span class="sxs-lookup"><span data-stu-id="a972d-106">Member</span></span>           | <span data-ttu-id="a972d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a972d-107">Description</span></span>                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| `rejitID`        | <span data-ttu-id="a972d-108">Il numero di revisione ReJit per un metodo.</span><span class="sxs-lookup"><span data-stu-id="a972d-108">The ReJit revision number for a method.</span></span>                                                          |
| `flags`          | <span data-ttu-id="a972d-109">Un flag che indica lo stato corrente della strumentazione ReJit del metodo per la versione specificata.</span><span class="sxs-lookup"><span data-stu-id="a972d-109">A flag indicating the current state of the method's ReJit instrumentation for the given version.</span></span> |
| `NativeCodeAddr` | <span data-ttu-id="a972d-110">L'indirizzo di base dell'implementazione rejitted del metodo.</span><span class="sxs-lookup"><span data-stu-id="a972d-110">The base address of the method's rejitted implementation.</span></span>                                         |

## <a name="remarks"></a><span data-ttu-id="a972d-111">Note</span><span class="sxs-lookup"><span data-stu-id="a972d-111">Remarks</span></span>

<span data-ttu-id="a972d-112">Questa struttura si trova all'interno del runtime e non viene esposto tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="a972d-112">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="a972d-113">Per usarlo, definire la struttura come specificato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="a972d-113">To use it, define the structure as specified above.</span></span> <span data-ttu-id="a972d-114">La struttura deve anche essere definita usando `ms_struct` compressione se non si utilizza i compilatori Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a972d-114">The structure must also be defined using `ms_struct` packing if not using the Microsoft compilers.</span></span>

## <a name="requirements"></a><span data-ttu-id="a972d-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a972d-115">Requirements</span></span>
<span data-ttu-id="a972d-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a972d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="a972d-117">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="a972d-117">**Header:** None</span></span>  
<span data-ttu-id="a972d-118">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="a972d-118">**Library:** None</span></span>  
**<span data-ttu-id="a972d-119">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="a972d-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a><span data-ttu-id="a972d-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a972d-120">See also</span></span>

- [<span data-ttu-id="a972d-121">Debug</span><span class="sxs-lookup"><span data-stu-id="a972d-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="a972d-122">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="a972d-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)

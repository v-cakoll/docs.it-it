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
ms.openlocfilehash: 974b99da085a5cb969ab37cddb0f2f2c62010d14
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828687"
---
# <a name="dacprejitdata-structure"></a><span data-ttu-id="8de65-102">DacpReJitData Structure</span><span class="sxs-lookup"><span data-stu-id="8de65-102">DacpReJitData Structure</span></span>

<span data-ttu-id="8de65-103">Definisce le informazioni di base per un determinato metodo instrumentato del profiler.</span><span class="sxs-lookup"><span data-stu-id="8de65-103">Defines the basic information about a given profiler-instrumented method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="8de65-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8de65-104">Syntax</span></span>

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

## <a name="members"></a><span data-ttu-id="8de65-105">Membri</span><span class="sxs-lookup"><span data-stu-id="8de65-105">Members</span></span>

| <span data-ttu-id="8de65-106">Membro</span><span class="sxs-lookup"><span data-stu-id="8de65-106">Member</span></span>           | <span data-ttu-id="8de65-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8de65-107">Description</span></span>                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| `rejitID`        | <span data-ttu-id="8de65-108">Il numero di revisione ReJit per un metodo.</span><span class="sxs-lookup"><span data-stu-id="8de65-108">The ReJit revision number for a method.</span></span>                                                          |
| `flags`          | <span data-ttu-id="8de65-109">Un flag che indica lo stato corrente della strumentazione ReJit del metodo per la versione specificata.</span><span class="sxs-lookup"><span data-stu-id="8de65-109">A flag indicating the current state of the method's ReJit instrumentation for the given version.</span></span> |
| `NativeCodeAddr` | <span data-ttu-id="8de65-110">L'indirizzo di base dell'implementazione rejitted del metodo.</span><span class="sxs-lookup"><span data-stu-id="8de65-110">The base address of the method's rejitted implementation.</span></span>                                         |


## <a name="remarks"></a><span data-ttu-id="8de65-111">Note</span><span class="sxs-lookup"><span data-stu-id="8de65-111">Remarks</span></span>

<span data-ttu-id="8de65-112">Questa struttura si trova all'interno del runtime e non viene esposto tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="8de65-112">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="8de65-113">Per usarlo, definire la struttura come specificato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="8de65-113">To use it, define the structure as specified above.</span></span> <span data-ttu-id="8de65-114">La struttura deve anche essere definita usando `ms_struct` compressione se non si utilizza i compilatori Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8de65-114">The structure must also be defined using `ms_struct` packing if not using the Microsoft compilers.</span></span>

## <a name="requirements"></a><span data-ttu-id="8de65-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8de65-115">Requirements</span></span>
<span data-ttu-id="8de65-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8de65-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="8de65-117">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="8de65-117">**Header:** None</span></span>  
<span data-ttu-id="8de65-118">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="8de65-118">**Library:** None</span></span>  
<span data-ttu-id="8de65-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8de65-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="8de65-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8de65-120">See also</span></span>
- [<span data-ttu-id="8de65-121">Debug</span><span class="sxs-lookup"><span data-stu-id="8de65-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="8de65-122">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="8de65-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)

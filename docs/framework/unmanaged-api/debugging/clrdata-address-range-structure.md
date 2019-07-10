---
title: Struttura CLRDATA_ADDRESS_RANGE
ms.date: 01/16/2019
api.name:
- CLRDATA_ADDRESS_RANGE Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- CLRDATA_ADDRESS_RANGE Structure
helpviewer.keywords:
- CLRDATA_ADDRESS_RANGE Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: afcb4e642c9b54107423f7474771fdc28cde709e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741020"
---
# <a name="clrdataaddressrange-structure"></a><span data-ttu-id="6a371-102">Struttura CLRDATA_ADDRESS_RANGE</span><span class="sxs-lookup"><span data-stu-id="6a371-102">CLRDATA_ADDRESS_RANGE Structure</span></span>

<span data-ttu-id="6a371-103">Definisce un intervallo di indirizzi.</span><span class="sxs-lookup"><span data-stu-id="6a371-103">Defines an address range.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="6a371-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6a371-104">Syntax</span></span>

```cpp
typedef struct
{
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
} CLRDATA_ADDRESS_RANGE;
```

## <a name="members"></a><span data-ttu-id="6a371-105">Membri</span><span class="sxs-lookup"><span data-stu-id="6a371-105">Members</span></span>

| <span data-ttu-id="6a371-106">Member</span><span class="sxs-lookup"><span data-stu-id="6a371-106">Member</span></span>         | <span data-ttu-id="6a371-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6a371-107">Description</span></span>                     |
| -------------- | ------------------------------- |
| `startAddress` | <span data-ttu-id="6a371-108">L'indirizzo iniziale dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="6a371-108">The start address of the range.</span></span> |
| `endAddress`   | <span data-ttu-id="6a371-109">L'indirizzo finale dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="6a371-109">The end address of the range.</span></span>   |

## <a name="remarks"></a><span data-ttu-id="6a371-110">Note</span><span class="sxs-lookup"><span data-stu-id="6a371-110">Remarks</span></span>

<span data-ttu-id="6a371-111">Questa struttura si trova all'interno del runtime e non viene esposto tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="6a371-111">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="6a371-112">Per usarlo, definire la struttura come specificato in precedenza, in cui `CLRDATA_ADDRESS` è un intero senza segno a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="6a371-112">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="6a371-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6a371-113">Requirements</span></span>

<span data-ttu-id="6a371-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a371-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="6a371-115">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="6a371-115">**Header:** None</span></span>  
<span data-ttu-id="6a371-116">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="6a371-116">**Library:** None</span></span>  
<span data-ttu-id="6a371-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6a371-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="6a371-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a371-118">See also</span></span>

- [<span data-ttu-id="6a371-119">Debug</span><span class="sxs-lookup"><span data-stu-id="6a371-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="6a371-120">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="6a371-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)

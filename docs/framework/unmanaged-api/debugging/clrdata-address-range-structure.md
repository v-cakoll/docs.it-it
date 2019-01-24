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
ms.openlocfilehash: 484ca79483fc4a5d8f0d1cf2cd5a961c297249e7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654802"
---
# <a name="clrdataaddressrange-structure"></a><span data-ttu-id="3d0bc-102">Struttura CLRDATA_ADDRESS_RANGE</span><span class="sxs-lookup"><span data-stu-id="3d0bc-102">CLRDATA_ADDRESS_RANGE Structure</span></span>

<span data-ttu-id="3d0bc-103">Definisce un intervallo di indirizzi.</span><span class="sxs-lookup"><span data-stu-id="3d0bc-103">Defines an address range.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="3d0bc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3d0bc-104">Syntax</span></span>

```
typedef struct
{
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
} CLRDATA_ADDRESS_RANGE;
```

## <a name="members"></a><span data-ttu-id="3d0bc-105">Membri</span><span class="sxs-lookup"><span data-stu-id="3d0bc-105">Members</span></span>

| <span data-ttu-id="3d0bc-106">Membro</span><span class="sxs-lookup"><span data-stu-id="3d0bc-106">Member</span></span>         | <span data-ttu-id="3d0bc-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3d0bc-107">Description</span></span>                     |
| -------------- | ------------------------------- |
| `startAddress` | <span data-ttu-id="3d0bc-108">L'indirizzo iniziale dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="3d0bc-108">The start address of the range.</span></span> |
| `endAddress`   | <span data-ttu-id="3d0bc-109">L'indirizzo finale dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="3d0bc-109">The end address of the range.</span></span>   |

## <a name="remarks"></a><span data-ttu-id="3d0bc-110">Note</span><span class="sxs-lookup"><span data-stu-id="3d0bc-110">Remarks</span></span>

<span data-ttu-id="3d0bc-111">Questa struttura si trova all'interno del runtime e non viene esposto tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="3d0bc-111">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="3d0bc-112">Per usarlo, definire la struttura come specificato in precedenza, in cui `CLRDATA_ADDRESS` è un intero senza segno a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="3d0bc-112">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="3d0bc-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3d0bc-113">Requirements</span></span>

<span data-ttu-id="3d0bc-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d0bc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="3d0bc-115">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="3d0bc-115">**Header:** None</span></span>  
<span data-ttu-id="3d0bc-116">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="3d0bc-116">**Library:** None</span></span>  
<span data-ttu-id="3d0bc-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3d0bc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="3d0bc-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d0bc-118">See also</span></span>

- [<span data-ttu-id="3d0bc-119">Debug</span><span class="sxs-lookup"><span data-stu-id="3d0bc-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="3d0bc-120">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="3d0bc-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)

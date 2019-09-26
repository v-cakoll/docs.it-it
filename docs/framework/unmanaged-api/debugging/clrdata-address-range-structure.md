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
ms.openlocfilehash: 8eb841b4c4f06a3932805ae6222bdd693def5ea0
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274304"
---
# <a name="clrdata_address_range-structure"></a><span data-ttu-id="142c5-102">Struttura CLRDATA_ADDRESS_RANGE</span><span class="sxs-lookup"><span data-stu-id="142c5-102">CLRDATA_ADDRESS_RANGE Structure</span></span>

<span data-ttu-id="142c5-103">Definisce un intervallo di indirizzi.</span><span class="sxs-lookup"><span data-stu-id="142c5-103">Defines an address range.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="142c5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="142c5-104">Syntax</span></span>

```cpp
typedef struct
{
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
} CLRDATA_ADDRESS_RANGE;
```

## <a name="members"></a><span data-ttu-id="142c5-105">Membri</span><span class="sxs-lookup"><span data-stu-id="142c5-105">Members</span></span>

| <span data-ttu-id="142c5-106">Member</span><span class="sxs-lookup"><span data-stu-id="142c5-106">Member</span></span>         | <span data-ttu-id="142c5-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="142c5-107">Description</span></span>                     |
| -------------- | ------------------------------- |
| `startAddress` | <span data-ttu-id="142c5-108">Indirizzo iniziale dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="142c5-108">The start address of the range.</span></span> |
| `endAddress`   | <span data-ttu-id="142c5-109">Indirizzo finale dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="142c5-109">The end address of the range.</span></span>   |

## <a name="remarks"></a><span data-ttu-id="142c5-110">Note</span><span class="sxs-lookup"><span data-stu-id="142c5-110">Remarks</span></span>

<span data-ttu-id="142c5-111">Questa struttura si trova all'interno del runtime e non viene esposta tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="142c5-111">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="142c5-112">Per usarlo, definire la struttura come specificato in precedenza, `CLRDATA_ADDRESS` dove è una Unsigned Integer a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="142c5-112">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="142c5-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="142c5-113">Requirements</span></span>

<span data-ttu-id="142c5-114">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="142c5-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="142c5-115">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="142c5-115">**Header:** None</span></span>  
<span data-ttu-id="142c5-116">**Libreria** nessuno</span><span class="sxs-lookup"><span data-stu-id="142c5-116">**Library:** None</span></span>  
<span data-ttu-id="142c5-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="142c5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="142c5-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="142c5-118">See also</span></span>

- [<span data-ttu-id="142c5-119">Debug</span><span class="sxs-lookup"><span data-stu-id="142c5-119">Debugging</span></span>](index.md)
- [<span data-ttu-id="142c5-120">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="142c5-120">Debugging Structures</span></span>](debugging-structures.md)

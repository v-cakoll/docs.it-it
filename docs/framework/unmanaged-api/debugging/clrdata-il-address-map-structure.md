---
title: Struttura CLRDATA_IL_ADDRESS_MAP
ms.date: 01/16/2019
api.name:
- CLRDATA_IL_ADDRESS_MAP Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- CLRDATA_IL_ADDRESS_MAP Structure
helpviewer.keywords:
- CLRDATA_IL_ADDRESS_MAP Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 3f6928832d822422177ebd7def142422953468a0
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274299"
---
# <a name="clrdata_il_address_map-structure"></a><span data-ttu-id="a5397-102">Struttura CLRDATA_IL_ADDRESS_MAP</span><span class="sxs-lookup"><span data-stu-id="a5397-102">CLRDATA_IL_ADDRESS_MAP Structure</span></span>

<span data-ttu-id="a5397-103">Definisce un valore IL per l'indirizzamento del mapping.</span><span class="sxs-lookup"><span data-stu-id="a5397-103">Defines an IL to address mapping.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="a5397-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a5397-104">Syntax</span></span>

```cpp
typedef struct
{
    ULONG32 ilOffset;
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
    CLRDataSourceType type;
} CLRDATA_IL_ADDRESS_MAP;
```

## <a name="members"></a><span data-ttu-id="a5397-105">Membri</span><span class="sxs-lookup"><span data-stu-id="a5397-105">Members</span></span>

| <span data-ttu-id="a5397-106">Member</span><span class="sxs-lookup"><span data-stu-id="a5397-106">Member</span></span>         | <span data-ttu-id="a5397-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a5397-107">Description</span></span>                                            |
| -------------- | ------------------------------------------------------ |
| `ilOffset`     | <span data-ttu-id="a5397-108">Offset IL per l'intervallo di indirizzi contenuti</span><span class="sxs-lookup"><span data-stu-id="a5397-108">IL offset for the contained address range</span></span>              |
| `startAddress` | <span data-ttu-id="a5397-109">Indirizzo iniziale dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="a5397-109">The start address of the range.</span></span>                        |
| `endAddress`   | <span data-ttu-id="a5397-110">Indirizzo finale dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="a5397-110">The end address of the range.</span></span>                          |
| `type`         | <span data-ttu-id="a5397-111">Tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="a5397-111">The type of the data.</span></span> <span data-ttu-id="a5397-112">Questo valore non è attualmente utilizzato</span><span class="sxs-lookup"><span data-stu-id="a5397-112">This value is currently not used</span></span> |

## <a name="remarks"></a><span data-ttu-id="a5397-113">Note</span><span class="sxs-lookup"><span data-stu-id="a5397-113">Remarks</span></span>

<span data-ttu-id="a5397-114">Questa struttura si trova all'interno del runtime e non viene esposta tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="a5397-114">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="a5397-115">Per usarlo, definire la struttura come specificato in precedenza, `CLRDATA_ADDRESS` dove è una Unsigned Integer a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="a5397-115">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="a5397-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a5397-116">Requirements</span></span>

<span data-ttu-id="a5397-117">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5397-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="a5397-118">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="a5397-118">**Header:** None</span></span>  
<span data-ttu-id="a5397-119">**Libreria** nessuno</span><span class="sxs-lookup"><span data-stu-id="a5397-119">**Library:** None</span></span>   
<span data-ttu-id="a5397-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a5397-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="a5397-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5397-121">See also</span></span>

- [<span data-ttu-id="a5397-122">Enumerazione CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="a5397-122">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="a5397-123">Debug</span><span class="sxs-lookup"><span data-stu-id="a5397-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="a5397-124">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="a5397-124">Debugging Structures</span></span>](debugging-structures.md)

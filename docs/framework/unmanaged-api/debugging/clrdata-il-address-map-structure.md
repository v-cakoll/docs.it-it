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
ms.openlocfilehash: e680a7a0dc3209d1988f6c84be0864572a74b3a4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179369"
---
# <a name="clrdata_il_address_map-structure"></a><span data-ttu-id="b4483-102">Struttura CLRDATA_IL_ADDRESS_MAP</span><span class="sxs-lookup"><span data-stu-id="b4483-102">CLRDATA_IL_ADDRESS_MAP Structure</span></span>

<span data-ttu-id="b4483-103">Definisce un linguaggio intermedio per il mapping degli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="b4483-103">Defines an IL to address mapping.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="b4483-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b4483-104">Syntax</span></span>

```cpp
typedef struct
{
    ULONG32 ilOffset;
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
    CLRDataSourceType type;
} CLRDATA_IL_ADDRESS_MAP;
```

## <a name="members"></a><span data-ttu-id="b4483-105">Members</span><span class="sxs-lookup"><span data-stu-id="b4483-105">Members</span></span>

| <span data-ttu-id="b4483-106">Membro</span><span class="sxs-lookup"><span data-stu-id="b4483-106">Member</span></span>         | <span data-ttu-id="b4483-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b4483-107">Description</span></span>                                            |
| -------------- | ------------------------------------------------------ |
| `ilOffset`     | <span data-ttu-id="b4483-108">Offset IL per l'intervallo di indirizzi contenuti</span><span class="sxs-lookup"><span data-stu-id="b4483-108">IL offset for the contained address range</span></span>              |
| `startAddress` | <span data-ttu-id="b4483-109">Indirizzo iniziale dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="b4483-109">The start address of the range.</span></span>                        |
| `endAddress`   | <span data-ttu-id="b4483-110">Indirizzo finale dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="b4483-110">The end address of the range.</span></span>                          |
| `type`         | <span data-ttu-id="b4483-111">Tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="b4483-111">The type of the data.</span></span> <span data-ttu-id="b4483-112">Questo valore non è attualmente utilizzato</span><span class="sxs-lookup"><span data-stu-id="b4483-112">This value is currently not used</span></span> |

## <a name="remarks"></a><span data-ttu-id="b4483-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b4483-113">Remarks</span></span>

<span data-ttu-id="b4483-114">Questa struttura si trova all'interno del runtime e non viene esposta tramite intestazioni o file di libreria.</span><span class="sxs-lookup"><span data-stu-id="b4483-114">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="b4483-115">Per utilizzarlo, definire la struttura `CLRDATA_ADDRESS` come specificato in precedenza, dove è un intero senza segno a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="b4483-115">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="b4483-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b4483-116">Requirements</span></span>

<span data-ttu-id="b4483-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4483-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b4483-118">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="b4483-118">**Header:** None</span></span>  
<span data-ttu-id="b4483-119">**Biblioteca:** Nessuno versioni di **.NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b4483-119">**Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b4483-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4483-120">See also</span></span>

- [<span data-ttu-id="b4483-121">Enumerazione CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="b4483-121">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="b4483-122">Debug</span><span class="sxs-lookup"><span data-stu-id="b4483-122">Debugging</span></span>](index.md)
- [<span data-ttu-id="b4483-123">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="b4483-123">Debugging Structures</span></span>](debugging-structures.md)

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
ms.openlocfilehash: 3aac7e24fa9cd03350aebf5f441063bcedfaed04
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54644768"
---
# <a name="clrdatailaddressmap-structure"></a><span data-ttu-id="3edc5-102">Struttura CLRDATA_IL_ADDRESS_MAP</span><span class="sxs-lookup"><span data-stu-id="3edc5-102">CLRDATA_IL_ADDRESS_MAP Structure</span></span>

<span data-ttu-id="3edc5-103">Definisce un livello di integrità per il mapping dell'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="3edc5-103">Defines an IL to address mapping.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="3edc5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3edc5-104">Syntax</span></span>

```
typedef struct
{
    ULONG32 ilOffset;
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
    CLRDataSourceType type;
} CLRDATA_IL_ADDRESS_MAP;
```

## <a name="members"></a><span data-ttu-id="3edc5-105">Membri</span><span class="sxs-lookup"><span data-stu-id="3edc5-105">Members</span></span>

| <span data-ttu-id="3edc5-106">Membro</span><span class="sxs-lookup"><span data-stu-id="3edc5-106">Member</span></span>         | <span data-ttu-id="3edc5-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3edc5-107">Description</span></span>                                            |
| -------------- | ------------------------------------------------------ |
| `ilOffset`     | <span data-ttu-id="3edc5-108">Offset IL per l'intervallo di indirizzi indipendente</span><span class="sxs-lookup"><span data-stu-id="3edc5-108">IL offset for the contained address range</span></span>              |
| `startAddress` | <span data-ttu-id="3edc5-109">L'indirizzo iniziale dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="3edc5-109">The start address of the range.</span></span>                        |
| `endAddress`   | <span data-ttu-id="3edc5-110">L'indirizzo finale dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="3edc5-110">The end address of the range.</span></span>                          |
| `type`         | <span data-ttu-id="3edc5-111">Tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="3edc5-111">The type of the data.</span></span> <span data-ttu-id="3edc5-112">Questo valore non è attualmente utilizzato</span><span class="sxs-lookup"><span data-stu-id="3edc5-112">This value is currently not used</span></span> |

## <a name="remarks"></a><span data-ttu-id="3edc5-113">Note</span><span class="sxs-lookup"><span data-stu-id="3edc5-113">Remarks</span></span>

<span data-ttu-id="3edc5-114">Questa struttura si trova all'interno del runtime e non viene esposto tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="3edc5-114">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="3edc5-115">Per usarlo, definire la struttura come specificato in precedenza, in cui `CLRDATA_ADDRESS` è un intero senza segno a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="3edc5-115">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="3edc5-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3edc5-116">Requirements</span></span>

<span data-ttu-id="3edc5-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3edc5-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="3edc5-118">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="3edc5-118">**Header:** None</span></span>  
<span data-ttu-id="3edc5-119">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="3edc5-119">**Library:** None</span></span>   
<span data-ttu-id="3edc5-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3edc5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="3edc5-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3edc5-121">See also</span></span>

- [<span data-ttu-id="3edc5-122">Enumerazione CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="3edc5-122">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="3edc5-123">Debug</span><span class="sxs-lookup"><span data-stu-id="3edc5-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="3edc5-124">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="3edc5-124">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)

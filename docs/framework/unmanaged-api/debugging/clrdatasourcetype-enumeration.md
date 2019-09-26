---
title: Enumerazione CLRDataSourceType
ms.date: 01/16/2019
api.name:
- CLRDataSourceType Enumeration
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- CLRDataSourceType Enumeration
helpviewer.keywords:
- CLRDataSourceType Enumeration [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 7ace405e2624f15b1cdb6d383222ae87c93289bb
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274101"
---
# <a name="clrdatasourcetype-enumeration"></a><span data-ttu-id="84165-102">Enumerazione CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="84165-102">CLRDataSourceType Enumeration</span></span>

<span data-ttu-id="84165-103">Fornisce i valori utilizzati dalla struttura CLRDATA_IL_ADDRESS_MAP.</span><span class="sxs-lookup"><span data-stu-id="84165-103">Provides values that are used by the CLRDATA_IL_ADDRESS_MAP structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="84165-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="84165-104">Syntax</span></span>

```cpp
typedef enum
{
    CLRDATA_SOURCE_TYPE_INVALID        = 0x00, // To indicate that nothing else applies
} CLRDataSourceType;
```

## <a name="members"></a><span data-ttu-id="84165-105">Membri</span><span class="sxs-lookup"><span data-stu-id="84165-105">Members</span></span>

| <span data-ttu-id="84165-106">Member</span><span class="sxs-lookup"><span data-stu-id="84165-106">Member</span></span>                        | <span data-ttu-id="84165-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84165-107">Description</span></span>                           |
| ----------------------------- | ------------------------------------- |
| `CLRDATA_SOURCE_TYPE_INVALID` | <span data-ttu-id="84165-108">Per indicare che non viene applicata alcuna altra operazione</span><span class="sxs-lookup"><span data-stu-id="84165-108">To indicate that nothing else applies</span></span> |

## <a name="remarks"></a><span data-ttu-id="84165-109">Note</span><span class="sxs-lookup"><span data-stu-id="84165-109">Remarks</span></span>

<span data-ttu-id="84165-110">Questa enumerazione si trova all'interno del runtime e non viene esposta tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="84165-110">This enumeration lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="84165-111">Per usarlo, definire un'enumerazione come definito in precedenza nel codice.</span><span class="sxs-lookup"><span data-stu-id="84165-111">To use it, define an enumeration as defined above in your code.</span></span> <span data-ttu-id="84165-112">Viene anche associato a `CLRDATA_ENUM` un alias come indicato nei [tipi di dati comuni](../common-data-types-unmanaged-api-reference.md).</span><span class="sxs-lookup"><span data-stu-id="84165-112">This is also aliased to `CLRDATA_ENUM` as mentioned in [Common Data Types](../common-data-types-unmanaged-api-reference.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="84165-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="84165-113">Requirements</span></span>

<span data-ttu-id="84165-114">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84165-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="84165-115">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="84165-115">**Header:** None</span></span>  
<span data-ttu-id="84165-116">**Libreria** nessuno</span><span class="sxs-lookup"><span data-stu-id="84165-116">**Library:** None</span></span>  
<span data-ttu-id="84165-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="84165-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="84165-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84165-118">See also</span></span>

- [<span data-ttu-id="84165-119">Debug</span><span class="sxs-lookup"><span data-stu-id="84165-119">Debugging</span></span>](index.md)
- [<span data-ttu-id="84165-120">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="84165-120">Debugging Enumerations</span></span>](debugging-enumerations.md)

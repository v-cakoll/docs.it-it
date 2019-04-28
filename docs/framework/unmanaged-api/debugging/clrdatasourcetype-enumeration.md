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
ms.openlocfilehash: c8b3f338659e2784db8deca3e1776e7926c30c32
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609698"
---
# <a name="clrdatasourcetype-enumeration"></a><span data-ttu-id="0a153-102">Enumerazione CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="0a153-102">CLRDataSourceType Enumeration</span></span>

<span data-ttu-id="0a153-103">Fornisce i valori utilizzati dalla struttura CLRDATA_IL_ADDRESS_MAP.</span><span class="sxs-lookup"><span data-stu-id="0a153-103">Provides values that are used by the CLRDATA_IL_ADDRESS_MAP structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="0a153-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0a153-104">Syntax</span></span>

```
typedef enum
{
    CLRDATA_SOURCE_TYPE_INVALID        = 0x00, // To indicate that nothing else applies
} CLRDataSourceType;
```

## <a name="members"></a><span data-ttu-id="0a153-105">Membri</span><span class="sxs-lookup"><span data-stu-id="0a153-105">Members</span></span>

| <span data-ttu-id="0a153-106">Member</span><span class="sxs-lookup"><span data-stu-id="0a153-106">Member</span></span>                        | <span data-ttu-id="0a153-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0a153-107">Description</span></span>                           |
| ----------------------------- | ------------------------------------- |
| `CLRDATA_SOURCE_TYPE_INVALID` | <span data-ttu-id="0a153-108">Per indicare che nessun altro elemento valida</span><span class="sxs-lookup"><span data-stu-id="0a153-108">To indicate that nothing else applies</span></span> |

## <a name="remarks"></a><span data-ttu-id="0a153-109">Note</span><span class="sxs-lookup"><span data-stu-id="0a153-109">Remarks</span></span>

<span data-ttu-id="0a153-110">Questa enumerazione si trova all'interno del runtime e non viene esposto tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="0a153-110">This enumeration lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="0a153-111">Per usarlo, definire un'enumerazione definita in precedenza nel codice.</span><span class="sxs-lookup"><span data-stu-id="0a153-111">To use it, define an enumeration as defined above in your code.</span></span> <span data-ttu-id="0a153-112">Questo è anche associato un alias per `CLRDATA_ENUM` come indicato nella [tipi di dati comuni](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).</span><span class="sxs-lookup"><span data-stu-id="0a153-112">This is also aliased to `CLRDATA_ENUM` as mentioned in [Common Data Types](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="0a153-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0a153-113">Requirements</span></span>

<span data-ttu-id="0a153-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a153-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="0a153-115">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="0a153-115">**Header:** None</span></span>  
<span data-ttu-id="0a153-116">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="0a153-116">**Library:** None</span></span>  
<span data-ttu-id="0a153-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0a153-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="0a153-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a153-118">See also</span></span>

- [<span data-ttu-id="0a153-119">Debug</span><span class="sxs-lookup"><span data-stu-id="0a153-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="0a153-120">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="0a153-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

---
title: Struttura DacpGetModuleAddress
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress Structure
helpviewer.keywords:
- DacpGetModuleAddress Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 1e3a62de3259c012438c64ece26e696682ec96e6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789200"
---
# <a name="dacpgetmoduleaddress-structure"></a><span data-ttu-id="7d970-102">Struttura DacpGetModuleAddress</span><span class="sxs-lookup"><span data-stu-id="7d970-102">DacpGetModuleAddress Structure</span></span>

<span data-ttu-id="7d970-103">Definisce il contenitore per una richiesta di indirizzo del modulo.</span><span class="sxs-lookup"><span data-stu-id="7d970-103">Defines the container for a module address request.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="7d970-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7d970-104">Syntax</span></span>

```cpp
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a><span data-ttu-id="7d970-105">Membri</span><span class="sxs-lookup"><span data-stu-id="7d970-105">Members</span></span>

| <span data-ttu-id="7d970-106">Member</span><span class="sxs-lookup"><span data-stu-id="7d970-106">Member</span></span>      | <span data-ttu-id="7d970-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d970-107">Description</span></span>                |
| ----------- | -------------------------- |
| `ModulePtr` | <span data-ttu-id="7d970-108">Puntatore al modulo.</span><span class="sxs-lookup"><span data-stu-id="7d970-108">The pointer to the module.</span></span> |

## <a name="methods"></a><span data-ttu-id="7d970-109">Metodi</span><span class="sxs-lookup"><span data-stu-id="7d970-109">Methods</span></span>

| <span data-ttu-id="7d970-110">Metodo</span><span class="sxs-lookup"><span data-stu-id="7d970-110">Method</span></span>                                                                                               | <span data-ttu-id="7d970-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d970-111">Description</span></span>                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [<span data-ttu-id="7d970-112">Richiesta</span><span class="sxs-lookup"><span data-stu-id="7d970-112">Request</span></span>](dacpgetmoduleaddress-request-method.md) | <span data-ttu-id="7d970-113">Esegue una richiesta per popolare la struttura dalla struttura di runtime specificata.</span><span class="sxs-lookup"><span data-stu-id="7d970-113">Performs a request to populate the structure from the given runtime structure.</span></span> |

## <a name="remarks"></a><span data-ttu-id="7d970-114">Note</span><span class="sxs-lookup"><span data-stu-id="7d970-114">Remarks</span></span>

<span data-ttu-id="7d970-115">Questa struttura si trova all'interno del runtime e non viene esposta tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="7d970-115">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="7d970-116">Per usarlo, definire la struttura come specificato in precedenza, dove `CLRDATA_ADDRESS` è un Unsigned Integer a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="7d970-116">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="7d970-117">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="7d970-117">Requirements</span></span>
<span data-ttu-id="7d970-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d970-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="7d970-119">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="7d970-119">**Header:** None</span></span>  
<span data-ttu-id="7d970-120">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="7d970-120">**Library:** None</span></span>  
<span data-ttu-id="7d970-121">**Versioni .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7d970-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="7d970-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d970-122">See also</span></span>

- [<span data-ttu-id="7d970-123">Debug</span><span class="sxs-lookup"><span data-stu-id="7d970-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="7d970-124">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="7d970-124">Debugging Structures</span></span>](debugging-structures.md)

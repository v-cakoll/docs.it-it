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
ms.openlocfilehash: ca9ce04e9a4770d46f88e10785f4dafd044c9212
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416531"
---
# <a name="dacpgetmoduleaddress-structure"></a><span data-ttu-id="6d00c-102">Struttura DacpGetModuleAddress</span><span class="sxs-lookup"><span data-stu-id="6d00c-102">DacpGetModuleAddress Structure</span></span>

<span data-ttu-id="6d00c-103">Definisce il contenitore per una richiesta del modulo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="6d00c-103">Defines the container for a module address request.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="6d00c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6d00c-104">Syntax</span></span>

```
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a><span data-ttu-id="6d00c-105">Membri</span><span class="sxs-lookup"><span data-stu-id="6d00c-105">Members</span></span>

| <span data-ttu-id="6d00c-106">Membro</span><span class="sxs-lookup"><span data-stu-id="6d00c-106">Member</span></span>      | <span data-ttu-id="6d00c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6d00c-107">Description</span></span>                |
| ----------- | -------------------------- |
| `ModulePtr` | <span data-ttu-id="6d00c-108">Il puntatore al modulo.</span><span class="sxs-lookup"><span data-stu-id="6d00c-108">The pointer to the module.</span></span> |

## <a name="methods"></a><span data-ttu-id="6d00c-109">Metodi</span><span class="sxs-lookup"><span data-stu-id="6d00c-109">Methods</span></span>

| <span data-ttu-id="6d00c-110">Metodo</span><span class="sxs-lookup"><span data-stu-id="6d00c-110">Method</span></span>                                                                                               | <span data-ttu-id="6d00c-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6d00c-111">Description</span></span>                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [<span data-ttu-id="6d00c-112">Richiesta</span><span class="sxs-lookup"><span data-stu-id="6d00c-112">Request</span></span>](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-request-method.md) | <span data-ttu-id="6d00c-113">Esegue una richiesta per popolare la struttura della struttura di runtime specificato.</span><span class="sxs-lookup"><span data-stu-id="6d00c-113">Performs a request to populate the structure from the given runtime structure.</span></span> |

## <a name="remarks"></a><span data-ttu-id="6d00c-114">Note</span><span class="sxs-lookup"><span data-stu-id="6d00c-114">Remarks</span></span>

<span data-ttu-id="6d00c-115">Questa struttura si trova all'interno del runtime e non viene esposto tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="6d00c-115">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="6d00c-116">Per usarlo, definire la struttura come specificato in precedenza, in cui `CLRDATA_ADDRESS` è un intero senza segno a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="6d00c-116">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="6d00c-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6d00c-117">Requirements</span></span>
<span data-ttu-id="6d00c-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d00c-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="6d00c-119">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="6d00c-119">**Header:** None</span></span>  
<span data-ttu-id="6d00c-120">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="6d00c-120">**Library:** None</span></span>  
<span data-ttu-id="6d00c-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6d00c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="6d00c-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d00c-122">See Also</span></span>
- [<span data-ttu-id="6d00c-123">Debug</span><span class="sxs-lookup"><span data-stu-id="6d00c-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="6d00c-124">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="6d00c-124">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)

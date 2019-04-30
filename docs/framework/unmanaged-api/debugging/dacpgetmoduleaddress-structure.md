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
ms.openlocfilehash: cbea6c0562c68ae5d18247dc97bc53eb9dfbfd7e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61965940"
---
# <a name="dacpgetmoduleaddress-structure"></a><span data-ttu-id="94be9-102">Struttura DacpGetModuleAddress</span><span class="sxs-lookup"><span data-stu-id="94be9-102">DacpGetModuleAddress Structure</span></span>

<span data-ttu-id="94be9-103">Definisce il contenitore per una richiesta del modulo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="94be9-103">Defines the container for a module address request.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="94be9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="94be9-104">Syntax</span></span>

```
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a><span data-ttu-id="94be9-105">Membri</span><span class="sxs-lookup"><span data-stu-id="94be9-105">Members</span></span>

| <span data-ttu-id="94be9-106">Member</span><span class="sxs-lookup"><span data-stu-id="94be9-106">Member</span></span>      | <span data-ttu-id="94be9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="94be9-107">Description</span></span>                |
| ----------- | -------------------------- |
| `ModulePtr` | <span data-ttu-id="94be9-108">Il puntatore al modulo.</span><span class="sxs-lookup"><span data-stu-id="94be9-108">The pointer to the module.</span></span> |

## <a name="methods"></a><span data-ttu-id="94be9-109">Metodi</span><span class="sxs-lookup"><span data-stu-id="94be9-109">Methods</span></span>

| <span data-ttu-id="94be9-110">Metodo</span><span class="sxs-lookup"><span data-stu-id="94be9-110">Method</span></span>                                                                                               | <span data-ttu-id="94be9-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="94be9-111">Description</span></span>                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [<span data-ttu-id="94be9-112">Richiesta</span><span class="sxs-lookup"><span data-stu-id="94be9-112">Request</span></span>](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-request-method.md) | <span data-ttu-id="94be9-113">Esegue una richiesta per popolare la struttura della struttura di runtime specificato.</span><span class="sxs-lookup"><span data-stu-id="94be9-113">Performs a request to populate the structure from the given runtime structure.</span></span> |

## <a name="remarks"></a><span data-ttu-id="94be9-114">Note</span><span class="sxs-lookup"><span data-stu-id="94be9-114">Remarks</span></span>

<span data-ttu-id="94be9-115">Questa struttura si trova all'interno del runtime e non viene esposto tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="94be9-115">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="94be9-116">Per usarlo, definire la struttura come specificato in precedenza, in cui `CLRDATA_ADDRESS` è un intero senza segno a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="94be9-116">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="94be9-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="94be9-117">Requirements</span></span>
<span data-ttu-id="94be9-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94be9-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="94be9-119">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="94be9-119">**Header:** None</span></span>  
<span data-ttu-id="94be9-120">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="94be9-120">**Library:** None</span></span>  
<span data-ttu-id="94be9-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="94be9-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="94be9-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94be9-122">See also</span></span>

- [<span data-ttu-id="94be9-123">Debug</span><span class="sxs-lookup"><span data-stu-id="94be9-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="94be9-124">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="94be9-124">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)

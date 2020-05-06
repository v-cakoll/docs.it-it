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
ms.openlocfilehash: e460264e2393858c028ba51aec4a4f2c01649994
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860833"
---
# <a name="dacpgetmoduleaddress-structure"></a><span data-ttu-id="d11a4-102">Struttura DacpGetModuleAddress</span><span class="sxs-lookup"><span data-stu-id="d11a4-102">DacpGetModuleAddress Structure</span></span>

<span data-ttu-id="d11a4-103">Definisce il contenitore per una richiesta di indirizzo del modulo.</span><span class="sxs-lookup"><span data-stu-id="d11a4-103">Defines the container for a module address request.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="d11a4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d11a4-104">Syntax</span></span>

```cpp
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a><span data-ttu-id="d11a4-105">Members</span><span class="sxs-lookup"><span data-stu-id="d11a4-105">Members</span></span>

| <span data-ttu-id="d11a4-106">Membro</span><span class="sxs-lookup"><span data-stu-id="d11a4-106">Member</span></span>      | <span data-ttu-id="d11a4-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d11a4-107">Description</span></span>                |
| ----------- | -------------------------- |
| `ModulePtr` | <span data-ttu-id="d11a4-108">Puntatore al modulo.</span><span class="sxs-lookup"><span data-stu-id="d11a4-108">The pointer to the module.</span></span> |

## <a name="methods"></a><span data-ttu-id="d11a4-109">Metodi</span><span class="sxs-lookup"><span data-stu-id="d11a4-109">Methods</span></span>

| <span data-ttu-id="d11a4-110">Metodo</span><span class="sxs-lookup"><span data-stu-id="d11a4-110">Method</span></span>                                                                                               | <span data-ttu-id="d11a4-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d11a4-111">Description</span></span>                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [<span data-ttu-id="d11a4-112">Richiesta</span><span class="sxs-lookup"><span data-stu-id="d11a4-112">Request</span></span>](dacpgetmoduleaddress-request-method.md) | <span data-ttu-id="d11a4-113">Esegue una richiesta per popolare la struttura dalla struttura di runtime specificata.</span><span class="sxs-lookup"><span data-stu-id="d11a4-113">Performs a request to populate the structure from the given runtime structure.</span></span> |

## <a name="remarks"></a><span data-ttu-id="d11a4-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d11a4-114">Remarks</span></span>

<span data-ttu-id="d11a4-115">Questa struttura si trova all'interno del runtime e non viene esposta tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="d11a4-115">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="d11a4-116">Per usarlo, definire la struttura come specificato in precedenza, `CLRDATA_ADDRESS` dove è una Unsigned Integer a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="d11a4-116">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="d11a4-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d11a4-117">Requirements</span></span>
<span data-ttu-id="d11a4-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d11a4-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="d11a4-119">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="d11a4-119">**Header:** None</span></span>  
<span data-ttu-id="d11a4-120">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="d11a4-120">**Library:** None</span></span>  
<span data-ttu-id="d11a4-121">**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d11a4-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="d11a4-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d11a4-122">See also</span></span>

- [<span data-ttu-id="d11a4-123">Debug</span><span class="sxs-lookup"><span data-stu-id="d11a4-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="d11a4-124">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="d11a4-124">Debugging Structures</span></span>](debugging-structures.md)

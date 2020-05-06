---
title: Struttura DacpModuleData
ms.date: 02/01/2019
api.name:
- DacpModuleData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpModuleData Structure
helpviewer.keywords:
- DacpModuleData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: e10d1792a8dc0b57ddd121ec09854e8e1824cade
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860797"
---
# <a name="dacpmoduledata-structure"></a><span data-ttu-id="2b63d-102">Struttura DacpModuleData</span><span class="sxs-lookup"><span data-stu-id="2b63d-102">DacpModuleData Structure</span></span>

<span data-ttu-id="2b63d-103">Definisce un buffer di trasporto per le informazioni di runtime di un modulo.</span><span class="sxs-lookup"><span data-stu-id="2b63d-103">Defines a transport buffer for a module's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="2b63d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2b63d-104">Syntax</span></span>

```cpp
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File;
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a><span data-ttu-id="2b63d-105">Members</span><span class="sxs-lookup"><span data-stu-id="2b63d-105">Members</span></span>

| <span data-ttu-id="2b63d-106">Membro</span><span class="sxs-lookup"><span data-stu-id="2b63d-106">Member</span></span>    | <span data-ttu-id="2b63d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b63d-107">Description</span></span>                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | <span data-ttu-id="2b63d-108">Indirizzo dell'oggetto modulo.</span><span class="sxs-lookup"><span data-stu-id="2b63d-108">Address of the module object.</span></span>                                           |
| `File`    | <span data-ttu-id="2b63d-109">Puntatore al file eseguibile di tipo PE.</span><span class="sxs-lookup"><span data-stu-id="2b63d-109">A pointer to the portable executable (PE) file.</span></span>                       |
| `ilBase`  | <span data-ttu-id="2b63d-110">Indirizzo della base dell'immagine caricata.</span><span class="sxs-lookup"><span data-stu-id="2b63d-110">The address of the loaded image's base.</span></span>                                 |
| `payLoad` | <span data-ttu-id="2b63d-111">Buffer del payload per informazioni aggiuntive sul modulo utilizzate dal runtime.</span><span class="sxs-lookup"><span data-stu-id="2b63d-111">A payload buffer for additional module information used by the runtime.</span></span> |

## <a name="remarks"></a><span data-ttu-id="2b63d-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2b63d-112">Remarks</span></span>

<span data-ttu-id="2b63d-113">Questa struttura si trova all'interno del runtime e non viene esposta tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="2b63d-113">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="2b63d-114">Per usarlo, definire la struttura come specificato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="2b63d-114">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="2b63d-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2b63d-115">Requirements</span></span>
<span data-ttu-id="2b63d-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b63d-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="2b63d-117">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="2b63d-117">**Header:** None</span></span>  
<span data-ttu-id="2b63d-118">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="2b63d-118">**Library:** None</span></span>  
<span data-ttu-id="2b63d-119">**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2b63d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="2b63d-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b63d-120">See also</span></span>

- [<span data-ttu-id="2b63d-121">Debug</span><span class="sxs-lookup"><span data-stu-id="2b63d-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="2b63d-122">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="2b63d-122">Debugging Structures</span></span>](debugging-structures.md)

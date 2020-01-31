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
ms.openlocfilehash: b46a04d67f59c5031b5bd195cef4cc2275e1e5e0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793801"
---
# <a name="dacpmoduledata-structure"></a><span data-ttu-id="e43b9-102">Struttura DacpModuleData</span><span class="sxs-lookup"><span data-stu-id="e43b9-102">DacpModuleData Structure</span></span>

<span data-ttu-id="e43b9-103">Definisce un buffer di trasporto per le informazioni di runtime di un modulo.</span><span class="sxs-lookup"><span data-stu-id="e43b9-103">Defines a transport buffer for a module's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="e43b9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e43b9-104">Syntax</span></span>

```cpp
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File; 
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a><span data-ttu-id="e43b9-105">Membri</span><span class="sxs-lookup"><span data-stu-id="e43b9-105">Members</span></span>

| <span data-ttu-id="e43b9-106">Member</span><span class="sxs-lookup"><span data-stu-id="e43b9-106">Member</span></span>    | <span data-ttu-id="e43b9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e43b9-107">Description</span></span>                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | <span data-ttu-id="e43b9-108">Indirizzo dell'oggetto modulo.</span><span class="sxs-lookup"><span data-stu-id="e43b9-108">Address of the module object.</span></span>                                           |
| `File`    | <span data-ttu-id="e43b9-109">Puntatore al file eseguibile di tipo PE.</span><span class="sxs-lookup"><span data-stu-id="e43b9-109">A pointer to the portable executable (PE) file.</span></span>                       |
| `ilBase`  | <span data-ttu-id="e43b9-110">Indirizzo della base dell'immagine caricata.</span><span class="sxs-lookup"><span data-stu-id="e43b9-110">The address of the loaded image's base.</span></span>                                 |
| `payLoad` | <span data-ttu-id="e43b9-111">Buffer del payload per informazioni aggiuntive sul modulo utilizzate dal runtime.</span><span class="sxs-lookup"><span data-stu-id="e43b9-111">A payload buffer for additional module information used by the runtime.</span></span> |

## <a name="remarks"></a><span data-ttu-id="e43b9-112">Note</span><span class="sxs-lookup"><span data-stu-id="e43b9-112">Remarks</span></span>

<span data-ttu-id="e43b9-113">Questa struttura si trova all'interno del runtime e non viene esposta tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="e43b9-113">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="e43b9-114">Per usarlo, definire la struttura come specificato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e43b9-114">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="e43b9-115">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="e43b9-115">Requirements</span></span>
<span data-ttu-id="e43b9-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e43b9-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="e43b9-117">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="e43b9-117">**Header:** None</span></span>  
<span data-ttu-id="e43b9-118">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="e43b9-118">**Library:** None</span></span>  
<span data-ttu-id="e43b9-119">**Versioni .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e43b9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="e43b9-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e43b9-120">See also</span></span>

- [<span data-ttu-id="e43b9-121">Debug</span><span class="sxs-lookup"><span data-stu-id="e43b9-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="e43b9-122">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="e43b9-122">Debugging Structures</span></span>](debugging-structures.md)

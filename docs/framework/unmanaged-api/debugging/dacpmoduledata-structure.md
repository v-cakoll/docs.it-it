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
ms.openlocfilehash: 2e27082ba4c35bc10eb65139b2af6c81c10d79a6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739116"
---
# <a name="dacpmoduledata-structure"></a><span data-ttu-id="c7d56-102">Struttura DacpModuleData</span><span class="sxs-lookup"><span data-stu-id="c7d56-102">DacpModuleData Structure</span></span>

<span data-ttu-id="c7d56-103">Definisce un buffer di trasporto per le informazioni di runtime del modulo.</span><span class="sxs-lookup"><span data-stu-id="c7d56-103">Defines a transport buffer for a module's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="c7d56-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c7d56-104">Syntax</span></span>

```cpp
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File; 
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a><span data-ttu-id="c7d56-105">Membri</span><span class="sxs-lookup"><span data-stu-id="c7d56-105">Members</span></span>

| <span data-ttu-id="c7d56-106">Member</span><span class="sxs-lookup"><span data-stu-id="c7d56-106">Member</span></span>    | <span data-ttu-id="c7d56-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c7d56-107">Description</span></span>                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | <span data-ttu-id="c7d56-108">Indirizzo dell'oggetto modulo.</span><span class="sxs-lookup"><span data-stu-id="c7d56-108">Address of the module object.</span></span>                                           |
| `File`    | <span data-ttu-id="c7d56-109">Un puntatore al file eseguibile portabile (PE).</span><span class="sxs-lookup"><span data-stu-id="c7d56-109">A pointer to the portable executable (PE) file.</span></span>                       |
| `ilBase`  | <span data-ttu-id="c7d56-110">Base dell'indirizzo dell'immagine caricata.</span><span class="sxs-lookup"><span data-stu-id="c7d56-110">The address of the loaded image's base.</span></span>                                 |
| `payLoad` | <span data-ttu-id="c7d56-111">Un buffer di payload per informazioni sul modulo aggiuntiva utilizzate dal runtime.</span><span class="sxs-lookup"><span data-stu-id="c7d56-111">A payload buffer for additional module information used by the runtime.</span></span> |

## <a name="remarks"></a><span data-ttu-id="c7d56-112">Note</span><span class="sxs-lookup"><span data-stu-id="c7d56-112">Remarks</span></span>

<span data-ttu-id="c7d56-113">Questa struttura si trova all'interno del runtime e non viene esposto tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="c7d56-113">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="c7d56-114">Per usarlo, definire la struttura come specificato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="c7d56-114">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="c7d56-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c7d56-115">Requirements</span></span>
<span data-ttu-id="c7d56-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7d56-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="c7d56-117">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="c7d56-117">**Header:** None</span></span>  
<span data-ttu-id="c7d56-118">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="c7d56-118">**Library:** None</span></span>  
<span data-ttu-id="c7d56-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c7d56-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="c7d56-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7d56-120">See also</span></span>

- [<span data-ttu-id="c7d56-121">Debug</span><span class="sxs-lookup"><span data-stu-id="c7d56-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="c7d56-122">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="c7d56-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)

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
ms.openlocfilehash: db3fdaa768e3d1b445f08c3964521570631f0965
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828667"
---
# <a name="dacpmoduledata-structure"></a><span data-ttu-id="74130-102">Struttura DacpModuleData</span><span class="sxs-lookup"><span data-stu-id="74130-102">DacpModuleData Structure</span></span>

<span data-ttu-id="74130-103">Definisce un buffer di trasporto per le informazioni di runtime del modulo.</span><span class="sxs-lookup"><span data-stu-id="74130-103">Defines a transport buffer for a module's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="74130-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="74130-104">Syntax</span></span>

```
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File; 
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a><span data-ttu-id="74130-105">Membri</span><span class="sxs-lookup"><span data-stu-id="74130-105">Members</span></span>

| <span data-ttu-id="74130-106">Membro</span><span class="sxs-lookup"><span data-stu-id="74130-106">Member</span></span>    | <span data-ttu-id="74130-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="74130-107">Description</span></span>                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | <span data-ttu-id="74130-108">Indirizzo dell'oggetto modulo.</span><span class="sxs-lookup"><span data-stu-id="74130-108">Address of the module object.</span></span>                                           |
| `File`    | <span data-ttu-id="74130-109">Un puntatore al file eseguibile portabile (PE).</span><span class="sxs-lookup"><span data-stu-id="74130-109">A pointer to the portable executable (PE) file.</span></span>                       |
| `ilBase`  | <span data-ttu-id="74130-110">Base dell'indirizzo dell'immagine caricata.</span><span class="sxs-lookup"><span data-stu-id="74130-110">The address of the loaded image's base.</span></span>                                 |
| `payLoad` | <span data-ttu-id="74130-111">Un buffer di payload per informazioni sul modulo aggiuntiva utilizzate dal runtime.</span><span class="sxs-lookup"><span data-stu-id="74130-111">A payload buffer for additional module information used by the runtime.</span></span> |


## <a name="remarks"></a><span data-ttu-id="74130-112">Note</span><span class="sxs-lookup"><span data-stu-id="74130-112">Remarks</span></span>

<span data-ttu-id="74130-113">Questa struttura si trova all'interno del runtime e non viene esposto tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="74130-113">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="74130-114">Per usarlo, definire la struttura come specificato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="74130-114">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="74130-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="74130-115">Requirements</span></span>
<span data-ttu-id="74130-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74130-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="74130-117">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="74130-117">**Header:** None</span></span>  
<span data-ttu-id="74130-118">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="74130-118">**Library:** None</span></span>  
<span data-ttu-id="74130-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="74130-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="74130-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74130-120">See also</span></span>
- [<span data-ttu-id="74130-121">Debug</span><span class="sxs-lookup"><span data-stu-id="74130-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="74130-122">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="74130-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)

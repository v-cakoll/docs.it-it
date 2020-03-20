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
ms.openlocfilehash: c24bdce64eb7e208bf3830940d7beab1ebf92e78
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179194"
---
# <a name="dacpmoduledata-structure"></a><span data-ttu-id="47cb3-102">Struttura DacpModuleData</span><span class="sxs-lookup"><span data-stu-id="47cb3-102">DacpModuleData Structure</span></span>

<span data-ttu-id="47cb3-103">Definisce un buffer di trasporto per le informazioni di runtime di un modulo.</span><span class="sxs-lookup"><span data-stu-id="47cb3-103">Defines a transport buffer for a module's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="47cb3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="47cb3-104">Syntax</span></span>

```cpp
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File;
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a><span data-ttu-id="47cb3-105">Members</span><span class="sxs-lookup"><span data-stu-id="47cb3-105">Members</span></span>

| <span data-ttu-id="47cb3-106">Membro</span><span class="sxs-lookup"><span data-stu-id="47cb3-106">Member</span></span>    | <span data-ttu-id="47cb3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="47cb3-107">Description</span></span>                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | <span data-ttu-id="47cb3-108">Indirizzo dell'oggetto modulo.</span><span class="sxs-lookup"><span data-stu-id="47cb3-108">Address of the module object.</span></span>                                           |
| `File`    | <span data-ttu-id="47cb3-109">Puntatore al file eseguibile portabile (PE).</span><span class="sxs-lookup"><span data-stu-id="47cb3-109">A pointer to the portable executable (PE) file.</span></span>                       |
| `ilBase`  | <span data-ttu-id="47cb3-110">Indirizzo della base dell'immagine caricata.</span><span class="sxs-lookup"><span data-stu-id="47cb3-110">The address of the loaded image's base.</span></span>                                 |
| `payLoad` | <span data-ttu-id="47cb3-111">Un buffer di payload per informazioni aggiuntive sul modulo utilizzate dal runtime.</span><span class="sxs-lookup"><span data-stu-id="47cb3-111">A payload buffer for additional module information used by the runtime.</span></span> |

## <a name="remarks"></a><span data-ttu-id="47cb3-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="47cb3-112">Remarks</span></span>

<span data-ttu-id="47cb3-113">Questa struttura si trova all'interno del runtime e non viene esposta tramite intestazioni o file di libreria.</span><span class="sxs-lookup"><span data-stu-id="47cb3-113">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="47cb3-114">Per utilizzarlo, definire la struttura come specificato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="47cb3-114">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="47cb3-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="47cb3-115">Requirements</span></span>
<span data-ttu-id="47cb3-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47cb3-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="47cb3-117">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="47cb3-117">**Header:** None</span></span>  
<span data-ttu-id="47cb3-118">**Biblioteca:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="47cb3-118">**Library:** None</span></span>  
<span data-ttu-id="47cb3-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="47cb3-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="47cb3-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47cb3-120">See also</span></span>

- [<span data-ttu-id="47cb3-121">Debug</span><span class="sxs-lookup"><span data-stu-id="47cb3-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="47cb3-122">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="47cb3-122">Debugging Structures</span></span>](debugging-structures.md)

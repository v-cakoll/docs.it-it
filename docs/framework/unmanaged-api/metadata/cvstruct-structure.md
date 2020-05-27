---
title: Struttura CVStruct
ms.date: 03/30/2017
api_name:
- CVStruct
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CVStruct
helpviewer_keywords:
- CVStruct structure [.NET Framework metadata]
ms.assetid: e9e4e497-d5fb-464b-991c-3bdd824664fd
topic_type:
- apiref
ms.openlocfilehash: 84791eba7c95d3278bd4650bd7d660e98fcb79d8
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008919"
---
# <a name="cvstruct-structure"></a><span data-ttu-id="2578e-102">Struttura CVStruct</span><span class="sxs-lookup"><span data-stu-id="2578e-102">CVStruct Structure</span></span>
<span data-ttu-id="2578e-103">Contiene informazioni usate durante l'installazione di un modulo o un'immagine composita.</span><span class="sxs-lookup"><span data-stu-id="2578e-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2578e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2578e-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="2578e-105">Membri</span><span class="sxs-lookup"><span data-stu-id="2578e-105">Members</span></span>  
  
|<span data-ttu-id="2578e-106">Membro</span><span class="sxs-lookup"><span data-stu-id="2578e-106">Member</span></span>|<span data-ttu-id="2578e-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2578e-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="2578e-108">Principale</span><span class="sxs-lookup"><span data-stu-id="2578e-108">Major</span></span>|<span data-ttu-id="2578e-109">Numero di build della versione principale.</span><span class="sxs-lookup"><span data-stu-id="2578e-109">Major version build number.</span></span>|  
|<span data-ttu-id="2578e-110">Minorenne</span><span class="sxs-lookup"><span data-stu-id="2578e-110">Minor</span></span>|<span data-ttu-id="2578e-111">Numero di build della versione secondaria.</span><span class="sxs-lookup"><span data-stu-id="2578e-111">Minor version build number.</span></span>|  
|<span data-ttu-id="2578e-112">Sub</span><span class="sxs-lookup"><span data-stu-id="2578e-112">Sub</span></span>|<span data-ttu-id="2578e-113">Numero di sottocompilazione.</span><span class="sxs-lookup"><span data-stu-id="2578e-113">Sub-build number.</span></span>|  
|<span data-ttu-id="2578e-114">Compilare</span><span class="sxs-lookup"><span data-stu-id="2578e-114">Build</span></span>|<span data-ttu-id="2578e-115">Numero di Build.</span><span class="sxs-lookup"><span data-stu-id="2578e-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2578e-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2578e-116">Requirements</span></span>  
 <span data-ttu-id="2578e-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2578e-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2578e-118">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2578e-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2578e-119">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2578e-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2578e-120">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2578e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2578e-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2578e-121">See also</span></span>

- [<span data-ttu-id="2578e-122">Strutture di metadati</span><span class="sxs-lookup"><span data-stu-id="2578e-122">Metadata Structures</span></span>](metadata-structures.md)

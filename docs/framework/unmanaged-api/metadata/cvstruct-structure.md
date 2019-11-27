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
ms.openlocfilehash: 19ee3097dfe80ba9dcbdaf316db0fd165b50abc6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436420"
---
# <a name="cvstruct-structure"></a><span data-ttu-id="faac9-102">Struttura CVStruct</span><span class="sxs-lookup"><span data-stu-id="faac9-102">CVStruct Structure</span></span>
<span data-ttu-id="faac9-103">Contiene informazioni usate durante l'installazione di un modulo o un'immagine composita.</span><span class="sxs-lookup"><span data-stu-id="faac9-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="faac9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="faac9-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="faac9-105">Membri</span><span class="sxs-lookup"><span data-stu-id="faac9-105">Members</span></span>  
  
|<span data-ttu-id="faac9-106">Membro</span><span class="sxs-lookup"><span data-stu-id="faac9-106">Member</span></span>|<span data-ttu-id="faac9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="faac9-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="faac9-108">Principale</span><span class="sxs-lookup"><span data-stu-id="faac9-108">Major</span></span>|<span data-ttu-id="faac9-109">Numero di build della versione principale.</span><span class="sxs-lookup"><span data-stu-id="faac9-109">Major version build number.</span></span>|  
|<span data-ttu-id="faac9-110">Secondaria</span><span class="sxs-lookup"><span data-stu-id="faac9-110">Minor</span></span>|<span data-ttu-id="faac9-111">Numero di build della versione secondaria.</span><span class="sxs-lookup"><span data-stu-id="faac9-111">Minor version build number.</span></span>|  
|<span data-ttu-id="faac9-112">risposta</span><span class="sxs-lookup"><span data-stu-id="faac9-112">Sub</span></span>|<span data-ttu-id="faac9-113">Numero di sottocompilazione.</span><span class="sxs-lookup"><span data-stu-id="faac9-113">Sub-build number.</span></span>|  
|<span data-ttu-id="faac9-114">Compila</span><span class="sxs-lookup"><span data-stu-id="faac9-114">Build</span></span>|<span data-ttu-id="faac9-115">Numero di build.</span><span class="sxs-lookup"><span data-stu-id="faac9-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="faac9-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="faac9-116">Requirements</span></span>  
 <span data-ttu-id="faac9-117">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="faac9-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="faac9-118">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="faac9-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="faac9-119">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="faac9-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="faac9-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="faac9-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faac9-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="faac9-121">See also</span></span>

- [<span data-ttu-id="faac9-122">Strutture di metadati</span><span class="sxs-lookup"><span data-stu-id="faac9-122">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)

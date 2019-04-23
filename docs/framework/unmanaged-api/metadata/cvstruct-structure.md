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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4a5f06b3f79fed5dac5a6f07650e4fabd0aa5867
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59142168"
---
# <a name="cvstruct-structure"></a><span data-ttu-id="cbd61-102">Struttura CVStruct</span><span class="sxs-lookup"><span data-stu-id="cbd61-102">CVStruct Structure</span></span>
<span data-ttu-id="cbd61-103">Contiene informazioni usate durante l'installazione di un modulo o un'immagine composita.</span><span class="sxs-lookup"><span data-stu-id="cbd61-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbd61-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cbd61-104">Syntax</span></span>  
  
```  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="cbd61-105">Membri</span><span class="sxs-lookup"><span data-stu-id="cbd61-105">Members</span></span>  
  
|<span data-ttu-id="cbd61-106">Member</span><span class="sxs-lookup"><span data-stu-id="cbd61-106">Member</span></span>|<span data-ttu-id="cbd61-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cbd61-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="cbd61-108">Principale</span><span class="sxs-lookup"><span data-stu-id="cbd61-108">Major</span></span>|<span data-ttu-id="cbd61-109">Numero di build di versione principale.</span><span class="sxs-lookup"><span data-stu-id="cbd61-109">Major version build number.</span></span>|  
|<span data-ttu-id="cbd61-110">Secondario</span><span class="sxs-lookup"><span data-stu-id="cbd61-110">Minor</span></span>|<span data-ttu-id="cbd61-111">Numero di build di versione secondario.</span><span class="sxs-lookup"><span data-stu-id="cbd61-111">Minor version build number.</span></span>|  
|<span data-ttu-id="cbd61-112">Sub</span><span class="sxs-lookup"><span data-stu-id="cbd61-112">Sub</span></span>|<span data-ttu-id="cbd61-113">Numero di build secondaria.</span><span class="sxs-lookup"><span data-stu-id="cbd61-113">Sub-build number.</span></span>|  
|<span data-ttu-id="cbd61-114">Compilazione</span><span class="sxs-lookup"><span data-stu-id="cbd61-114">Build</span></span>|<span data-ttu-id="cbd61-115">numero di build.</span><span class="sxs-lookup"><span data-stu-id="cbd61-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cbd61-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cbd61-116">Requirements</span></span>  
 <span data-ttu-id="cbd61-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbd61-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbd61-118">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="cbd61-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cbd61-119">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="cbd61-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cbd61-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbd61-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbd61-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cbd61-121">See also</span></span>

- [<span data-ttu-id="cbd61-122">Strutture di metadati</span><span class="sxs-lookup"><span data-stu-id="cbd61-122">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)

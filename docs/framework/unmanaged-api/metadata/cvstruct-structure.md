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
ms.openlocfilehash: fb73980faa64464c572945fe5ad04e015dc8805b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720652"
---
# <a name="cvstruct-structure"></a><span data-ttu-id="8573c-102">Struttura CVStruct</span><span class="sxs-lookup"><span data-stu-id="8573c-102">CVStruct Structure</span></span>
<span data-ttu-id="8573c-103">Contiene informazioni usate durante l'installazione di un modulo o un'immagine composita.</span><span class="sxs-lookup"><span data-stu-id="8573c-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8573c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8573c-104">Syntax</span></span>  
  
```  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="8573c-105">Membri</span><span class="sxs-lookup"><span data-stu-id="8573c-105">Members</span></span>  
  
|<span data-ttu-id="8573c-106">Membro</span><span class="sxs-lookup"><span data-stu-id="8573c-106">Member</span></span>|<span data-ttu-id="8573c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8573c-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="8573c-108">Principale</span><span class="sxs-lookup"><span data-stu-id="8573c-108">Major</span></span>|<span data-ttu-id="8573c-109">Numero di build di versione principale.</span><span class="sxs-lookup"><span data-stu-id="8573c-109">Major version build number.</span></span>|  
|<span data-ttu-id="8573c-110">Secondario</span><span class="sxs-lookup"><span data-stu-id="8573c-110">Minor</span></span>|<span data-ttu-id="8573c-111">Numero di build di versione secondario.</span><span class="sxs-lookup"><span data-stu-id="8573c-111">Minor version build number.</span></span>|  
|<span data-ttu-id="8573c-112">Sub</span><span class="sxs-lookup"><span data-stu-id="8573c-112">Sub</span></span>|<span data-ttu-id="8573c-113">Numero di build secondaria.</span><span class="sxs-lookup"><span data-stu-id="8573c-113">Sub-build number.</span></span>|  
|<span data-ttu-id="8573c-114">Compilazione</span><span class="sxs-lookup"><span data-stu-id="8573c-114">Build</span></span>|<span data-ttu-id="8573c-115">numero di build.</span><span class="sxs-lookup"><span data-stu-id="8573c-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8573c-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8573c-116">Requirements</span></span>  
 <span data-ttu-id="8573c-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8573c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8573c-118">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8573c-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8573c-119">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="8573c-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8573c-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8573c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8573c-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8573c-121">See also</span></span>
- [<span data-ttu-id="8573c-122">Strutture di metadati</span><span class="sxs-lookup"><span data-stu-id="8573c-122">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)

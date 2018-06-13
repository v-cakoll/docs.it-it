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
ms.openlocfilehash: 195f311d58f2169d715bb33986ee6e591622f377
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445043"
---
# <a name="cvstruct-structure"></a><span data-ttu-id="81c57-102">Struttura CVStruct</span><span class="sxs-lookup"><span data-stu-id="81c57-102">CVStruct Structure</span></span>
<span data-ttu-id="81c57-103">Contiene informazioni usate durante l'installazione di un modulo o un'immagine composita.</span><span class="sxs-lookup"><span data-stu-id="81c57-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81c57-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="81c57-104">Syntax</span></span>  
  
```  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="81c57-105">Membri</span><span class="sxs-lookup"><span data-stu-id="81c57-105">Members</span></span>  
  
|<span data-ttu-id="81c57-106">Membro</span><span class="sxs-lookup"><span data-stu-id="81c57-106">Member</span></span>|<span data-ttu-id="81c57-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="81c57-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="81c57-108">Principale</span><span class="sxs-lookup"><span data-stu-id="81c57-108">Major</span></span>|<span data-ttu-id="81c57-109">Numero di build di versione principale.</span><span class="sxs-lookup"><span data-stu-id="81c57-109">Major version build number.</span></span>|  
|<span data-ttu-id="81c57-110">Secondario</span><span class="sxs-lookup"><span data-stu-id="81c57-110">Minor</span></span>|<span data-ttu-id="81c57-111">Numero di build di versione secondario.</span><span class="sxs-lookup"><span data-stu-id="81c57-111">Minor version build number.</span></span>|  
|<span data-ttu-id="81c57-112">Sub</span><span class="sxs-lookup"><span data-stu-id="81c57-112">Sub</span></span>|<span data-ttu-id="81c57-113">Numero di build secondaria.</span><span class="sxs-lookup"><span data-stu-id="81c57-113">Sub-build number.</span></span>|  
|<span data-ttu-id="81c57-114">Compilazione</span><span class="sxs-lookup"><span data-stu-id="81c57-114">Build</span></span>|<span data-ttu-id="81c57-115">Numero di build.</span><span class="sxs-lookup"><span data-stu-id="81c57-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="81c57-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="81c57-116">Requirements</span></span>  
 <span data-ttu-id="81c57-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81c57-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81c57-118">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="81c57-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="81c57-119">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="81c57-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="81c57-120">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81c57-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81c57-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81c57-121">See Also</span></span>  
 [<span data-ttu-id="81c57-122">Strutture di metadati</span><span class="sxs-lookup"><span data-stu-id="81c57-122">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)

---
title: Struttura CVStruct
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CVStruct
api_location: mscoree.dll
api_type: COM
f1_keywords: CVStruct
helpviewer_keywords: CVStruct structure [.NET Framework metadata]
ms.assetid: e9e4e497-d5fb-464b-991c-3bdd824664fd
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2e0c9087b180b39185fbf66235b515b9742e69ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="cvstruct-structure"></a><span data-ttu-id="b9565-102">Struttura CVStruct</span><span class="sxs-lookup"><span data-stu-id="b9565-102">CVStruct Structure</span></span>
<span data-ttu-id="b9565-103">Contiene informazioni usate durante l'installazione di un modulo o un'immagine composita.</span><span class="sxs-lookup"><span data-stu-id="b9565-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9565-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b9565-104">Syntax</span></span>  
  
```  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="b9565-105">Membri</span><span class="sxs-lookup"><span data-stu-id="b9565-105">Members</span></span>  
  
|<span data-ttu-id="b9565-106">Membro</span><span class="sxs-lookup"><span data-stu-id="b9565-106">Member</span></span>|<span data-ttu-id="b9565-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b9565-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="b9565-108">Principale</span><span class="sxs-lookup"><span data-stu-id="b9565-108">Major</span></span>|<span data-ttu-id="b9565-109">Numero di build di versione principale.</span><span class="sxs-lookup"><span data-stu-id="b9565-109">Major version build number.</span></span>|  
|<span data-ttu-id="b9565-110">Secondario</span><span class="sxs-lookup"><span data-stu-id="b9565-110">Minor</span></span>|<span data-ttu-id="b9565-111">Numero di build di versione secondario.</span><span class="sxs-lookup"><span data-stu-id="b9565-111">Minor version build number.</span></span>|  
|<span data-ttu-id="b9565-112">Sub</span><span class="sxs-lookup"><span data-stu-id="b9565-112">Sub</span></span>|<span data-ttu-id="b9565-113">Numero di build secondaria.</span><span class="sxs-lookup"><span data-stu-id="b9565-113">Sub-build number.</span></span>|  
|<span data-ttu-id="b9565-114">Compilazione</span><span class="sxs-lookup"><span data-stu-id="b9565-114">Build</span></span>|<span data-ttu-id="b9565-115">Numero di build.</span><span class="sxs-lookup"><span data-stu-id="b9565-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b9565-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b9565-116">Requirements</span></span>  
 <span data-ttu-id="b9565-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9565-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9565-118">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b9565-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b9565-119">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b9565-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b9565-120">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9565-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9565-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9565-121">See Also</span></span>  
 [<span data-ttu-id="b9565-122">Strutture di metadati</span><span class="sxs-lookup"><span data-stu-id="b9565-122">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)

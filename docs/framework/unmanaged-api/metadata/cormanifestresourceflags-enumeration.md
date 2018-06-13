---
title: Enumerazione CorManifestResourceFlags
ms.date: 03/30/2017
api_name:
- CorManifestResourceFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorManifestResourceFlags
helpviewer_keywords:
- CorManifestResourceFlags enumeration [.NET Framework metadata]
ms.assetid: 1b0306b7-622b-4b57-8edc-3c713bb147ae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 21cce26c94d26f6c079fca644a31bf83cd1a6432
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440710"
---
# <a name="cormanifestresourceflags-enumeration"></a><span data-ttu-id="46eb3-102">Enumerazione CorManifestResourceFlags</span><span class="sxs-lookup"><span data-stu-id="46eb3-102">CorManifestResourceFlags Enumeration</span></span>
<span data-ttu-id="46eb3-103">Indica la visibilità delle risorse codificate in un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="46eb3-103">Indicates the visibility of resources encoded in an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46eb3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="46eb3-104">Syntax</span></span>  
  
```  
typedef enum CorManifestResourceFlags {  
  
    mrVisibilityMask        =   0x0007,  
    mrPublic                =   0x0001,  
    mrPrivate               =   0x0002  
  
} CorManifestResourceFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="46eb3-105">Membri</span><span class="sxs-lookup"><span data-stu-id="46eb3-105">Members</span></span>  
  
|<span data-ttu-id="46eb3-106">Membro</span><span class="sxs-lookup"><span data-stu-id="46eb3-106">Member</span></span>|<span data-ttu-id="46eb3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="46eb3-107">Description</span></span>|  
|------------|-----------------|  
|`mrVisibilityMask`|<span data-ttu-id="46eb3-108">Riservato.</span><span class="sxs-lookup"><span data-stu-id="46eb3-108">Reserved.</span></span>|  
|`mrPublic`|<span data-ttu-id="46eb3-109">Le risorse sono pubbliche.</span><span class="sxs-lookup"><span data-stu-id="46eb3-109">The resources are public.</span></span>|  
|`mrPrivate`|<span data-ttu-id="46eb3-110">Le risorse sono private.</span><span class="sxs-lookup"><span data-stu-id="46eb3-110">The resources are private.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="46eb3-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="46eb3-111">Requirements</span></span>  
 <span data-ttu-id="46eb3-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46eb3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46eb3-113">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="46eb3-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="46eb3-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46eb3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46eb3-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46eb3-115">See Also</span></span>  
 [<span data-ttu-id="46eb3-116">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="46eb3-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

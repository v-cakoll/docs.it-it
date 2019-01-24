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
ms.openlocfilehash: a3d3ef78da9dd639d0f9050a8b61d1e365cd8b42
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54650249"
---
# <a name="cormanifestresourceflags-enumeration"></a><span data-ttu-id="d25ad-102">Enumerazione CorManifestResourceFlags</span><span class="sxs-lookup"><span data-stu-id="d25ad-102">CorManifestResourceFlags Enumeration</span></span>
<span data-ttu-id="d25ad-103">Indica la visibilità delle risorse codificate in un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="d25ad-103">Indicates the visibility of resources encoded in an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d25ad-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d25ad-104">Syntax</span></span>  
  
```  
typedef enum CorManifestResourceFlags {  
  
    mrVisibilityMask        =   0x0007,  
    mrPublic                =   0x0001,  
    mrPrivate               =   0x0002  
  
} CorManifestResourceFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="d25ad-105">Membri</span><span class="sxs-lookup"><span data-stu-id="d25ad-105">Members</span></span>  
  
|<span data-ttu-id="d25ad-106">Membro</span><span class="sxs-lookup"><span data-stu-id="d25ad-106">Member</span></span>|<span data-ttu-id="d25ad-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d25ad-107">Description</span></span>|  
|------------|-----------------|  
|`mrVisibilityMask`|<span data-ttu-id="d25ad-108">Riservato.</span><span class="sxs-lookup"><span data-stu-id="d25ad-108">Reserved.</span></span>|  
|`mrPublic`|<span data-ttu-id="d25ad-109">Le risorse sono pubbliche.</span><span class="sxs-lookup"><span data-stu-id="d25ad-109">The resources are public.</span></span>|  
|`mrPrivate`|<span data-ttu-id="d25ad-110">Le risorse sono private.</span><span class="sxs-lookup"><span data-stu-id="d25ad-110">The resources are private.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d25ad-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d25ad-111">Requirements</span></span>  
 <span data-ttu-id="d25ad-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d25ad-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d25ad-113">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="d25ad-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="d25ad-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d25ad-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d25ad-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d25ad-115">See also</span></span>
- [<span data-ttu-id="d25ad-116">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="d25ad-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

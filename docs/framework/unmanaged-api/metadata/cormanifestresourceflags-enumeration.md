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
ms.openlocfilehash: 204f04b1ed1ea293639e0b9826f7e0ce6f384763
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59198543"
---
# <a name="cormanifestresourceflags-enumeration"></a><span data-ttu-id="bdf34-102">Enumerazione CorManifestResourceFlags</span><span class="sxs-lookup"><span data-stu-id="bdf34-102">CorManifestResourceFlags Enumeration</span></span>
<span data-ttu-id="bdf34-103">Indica la visibilità delle risorse codificate in un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="bdf34-103">Indicates the visibility of resources encoded in an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdf34-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bdf34-104">Syntax</span></span>  
  
```  
typedef enum CorManifestResourceFlags {  
  
    mrVisibilityMask        =   0x0007,  
    mrPublic                =   0x0001,  
    mrPrivate               =   0x0002  
  
} CorManifestResourceFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="bdf34-105">Membri</span><span class="sxs-lookup"><span data-stu-id="bdf34-105">Members</span></span>  
  
|<span data-ttu-id="bdf34-106">Member</span><span class="sxs-lookup"><span data-stu-id="bdf34-106">Member</span></span>|<span data-ttu-id="bdf34-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bdf34-107">Description</span></span>|  
|------------|-----------------|  
|`mrVisibilityMask`|<span data-ttu-id="bdf34-108">Riservato.</span><span class="sxs-lookup"><span data-stu-id="bdf34-108">Reserved.</span></span>|  
|`mrPublic`|<span data-ttu-id="bdf34-109">Le risorse sono pubbliche.</span><span class="sxs-lookup"><span data-stu-id="bdf34-109">The resources are public.</span></span>|  
|`mrPrivate`|<span data-ttu-id="bdf34-110">Le risorse sono private.</span><span class="sxs-lookup"><span data-stu-id="bdf34-110">The resources are private.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bdf34-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bdf34-111">Requirements</span></span>  
 <span data-ttu-id="bdf34-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bdf34-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdf34-113">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="bdf34-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="bdf34-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdf34-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdf34-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bdf34-115">See also</span></span>

- [<span data-ttu-id="bdf34-116">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="bdf34-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

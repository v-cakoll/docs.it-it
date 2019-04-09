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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198543"
---
# <a name="cormanifestresourceflags-enumeration"></a><span data-ttu-id="53883-102">Enumerazione CorManifestResourceFlags</span><span class="sxs-lookup"><span data-stu-id="53883-102">CorManifestResourceFlags Enumeration</span></span>
<span data-ttu-id="53883-103">Indica la visibilità delle risorse codificate in un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="53883-103">Indicates the visibility of resources encoded in an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53883-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="53883-104">Syntax</span></span>  
  
```  
typedef enum CorManifestResourceFlags {  
  
    mrVisibilityMask        =   0x0007,  
    mrPublic                =   0x0001,  
    mrPrivate               =   0x0002  
  
} CorManifestResourceFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="53883-105">Membri</span><span class="sxs-lookup"><span data-stu-id="53883-105">Members</span></span>  
  
|<span data-ttu-id="53883-106">Member</span><span class="sxs-lookup"><span data-stu-id="53883-106">Member</span></span>|<span data-ttu-id="53883-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53883-107">Description</span></span>|  
|------------|-----------------|  
|`mrVisibilityMask`|<span data-ttu-id="53883-108">Riservato.</span><span class="sxs-lookup"><span data-stu-id="53883-108">Reserved.</span></span>|  
|`mrPublic`|<span data-ttu-id="53883-109">Le risorse sono pubbliche.</span><span class="sxs-lookup"><span data-stu-id="53883-109">The resources are public.</span></span>|  
|`mrPrivate`|<span data-ttu-id="53883-110">Le risorse sono private.</span><span class="sxs-lookup"><span data-stu-id="53883-110">The resources are private.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="53883-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="53883-111">Requirements</span></span>  
 <span data-ttu-id="53883-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53883-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53883-113">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="53883-113">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="53883-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="53883-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="53883-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53883-115">See also</span></span>

- [<span data-ttu-id="53883-116">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="53883-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

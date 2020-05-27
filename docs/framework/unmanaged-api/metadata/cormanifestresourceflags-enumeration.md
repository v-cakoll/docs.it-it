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
ms.openlocfilehash: ebdff88e9fdf499b809d56c4c29a906dbef9ec40
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008976"
---
# <a name="cormanifestresourceflags-enumeration"></a><span data-ttu-id="c245d-102">Enumerazione CorManifestResourceFlags</span><span class="sxs-lookup"><span data-stu-id="c245d-102">CorManifestResourceFlags Enumeration</span></span>
<span data-ttu-id="c245d-103">Indica la visibilità delle risorse codificate in un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c245d-103">Indicates the visibility of resources encoded in an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c245d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c245d-104">Syntax</span></span>  
  
```cpp  
typedef enum CorManifestResourceFlags {  
  
    mrVisibilityMask        =   0x0007,  
    mrPublic                =   0x0001,  
    mrPrivate               =   0x0002  
  
} CorManifestResourceFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="c245d-105">Membri</span><span class="sxs-lookup"><span data-stu-id="c245d-105">Members</span></span>  
  
|<span data-ttu-id="c245d-106">Membro</span><span class="sxs-lookup"><span data-stu-id="c245d-106">Member</span></span>|<span data-ttu-id="c245d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c245d-107">Description</span></span>|  
|------------|-----------------|  
|`mrVisibilityMask`|<span data-ttu-id="c245d-108">Riservato.</span><span class="sxs-lookup"><span data-stu-id="c245d-108">Reserved.</span></span>|  
|`mrPublic`|<span data-ttu-id="c245d-109">Le risorse sono pubbliche.</span><span class="sxs-lookup"><span data-stu-id="c245d-109">The resources are public.</span></span>|  
|`mrPrivate`|<span data-ttu-id="c245d-110">Le risorse sono private.</span><span class="sxs-lookup"><span data-stu-id="c245d-110">The resources are private.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c245d-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c245d-111">Requirements</span></span>  
 <span data-ttu-id="c245d-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c245d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c245d-113">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="c245d-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c245d-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c245d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c245d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c245d-115">See also</span></span>

- [<span data-ttu-id="c245d-116">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="c245d-116">Metadata Enumerations</span></span>](metadata-enumerations.md)

---
title: Enumerazione CorEventAttr
ms.date: 03/30/2017
api_name:
- CorEventAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorEventAttr
helpviewer_keywords:
- CorEventAttr enumeration [.NET Framework metadata]
ms.assetid: dc2b3281-3820-487e-930d-350b66dc6417
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a1a50c15071ea1e696e508c779309225c7e7bfa2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097821"
---
# <a name="coreventattr-enumeration"></a><span data-ttu-id="e45ef-102">Enumerazione CorEventAttr</span><span class="sxs-lookup"><span data-stu-id="e45ef-102">CorEventAttr Enumeration</span></span>
<span data-ttu-id="e45ef-103">Contiene valori che descrivono i metadati di un evento.</span><span class="sxs-lookup"><span data-stu-id="e45ef-103">Contains values that describe the metadata of an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e45ef-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e45ef-104">Syntax</span></span>  
  
```  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="e45ef-105">Membri</span><span class="sxs-lookup"><span data-stu-id="e45ef-105">Members</span></span>  
  
|<span data-ttu-id="e45ef-106">Member</span><span class="sxs-lookup"><span data-stu-id="e45ef-106">Member</span></span>|<span data-ttu-id="e45ef-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e45ef-107">Description</span></span>|  
|------------|-----------------|  
|`evSpecialName`|<span data-ttu-id="e45ef-108">Specifica che l'evento è speciale e che il relativo nome viene descritto come.</span><span class="sxs-lookup"><span data-stu-id="e45ef-108">Specifies that the event is special, and that its name describes how.</span></span>|  
|`evReservedMask`|<span data-ttu-id="e45ef-109">Riservato per uso interno da common language runtime.</span><span class="sxs-lookup"><span data-stu-id="e45ef-109">Reserved for internal use by the common language runtime.</span></span>|  
|`evRTSpecialName`|<span data-ttu-id="e45ef-110">Specifica che common language runtime deve verificare la codifica il nome dell'evento.</span><span class="sxs-lookup"><span data-stu-id="e45ef-110">Specifies that the common language runtime should check the encoding of the event name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e45ef-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e45ef-111">Requirements</span></span>  
 <span data-ttu-id="e45ef-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e45ef-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e45ef-113">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="e45ef-113">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="e45ef-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e45ef-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e45ef-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e45ef-115">See also</span></span>

- [<span data-ttu-id="e45ef-116">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="e45ef-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

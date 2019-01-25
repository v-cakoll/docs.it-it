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
ms.openlocfilehash: d34aa954126cc26519aaea963f99299e5557d2c8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743052"
---
# <a name="coreventattr-enumeration"></a><span data-ttu-id="7e88a-102">Enumerazione CorEventAttr</span><span class="sxs-lookup"><span data-stu-id="7e88a-102">CorEventAttr Enumeration</span></span>
<span data-ttu-id="7e88a-103">Contiene valori che descrivono i metadati di un evento.</span><span class="sxs-lookup"><span data-stu-id="7e88a-103">Contains values that describe the metadata of an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e88a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7e88a-104">Syntax</span></span>  
  
```  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="7e88a-105">Membri</span><span class="sxs-lookup"><span data-stu-id="7e88a-105">Members</span></span>  
  
|<span data-ttu-id="7e88a-106">Membro</span><span class="sxs-lookup"><span data-stu-id="7e88a-106">Member</span></span>|<span data-ttu-id="7e88a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7e88a-107">Description</span></span>|  
|------------|-----------------|  
|`evSpecialName`|<span data-ttu-id="7e88a-108">Specifica che l'evento è speciale e che il relativo nome viene descritto come.</span><span class="sxs-lookup"><span data-stu-id="7e88a-108">Specifies that the event is special, and that its name describes how.</span></span>|  
|`evReservedMask`|<span data-ttu-id="7e88a-109">Riservato per uso interno da common language runtime.</span><span class="sxs-lookup"><span data-stu-id="7e88a-109">Reserved for internal use by the common language runtime.</span></span>|  
|`evRTSpecialName`|<span data-ttu-id="7e88a-110">Specifica che common language runtime deve verificare la codifica il nome dell'evento.</span><span class="sxs-lookup"><span data-stu-id="7e88a-110">Specifies that the common language runtime should check the encoding of the event name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7e88a-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7e88a-111">Requirements</span></span>  
 <span data-ttu-id="7e88a-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e88a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e88a-113">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="7e88a-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="7e88a-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e88a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e88a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e88a-115">See also</span></span>
- [<span data-ttu-id="7e88a-116">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="7e88a-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

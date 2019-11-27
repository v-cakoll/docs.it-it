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
ms.openlocfilehash: ec2972605c40f4ba292f5a5f58d6d3efed53f966
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443567"
---
# <a name="coreventattr-enumeration"></a><span data-ttu-id="a3cdc-102">Enumerazione CorEventAttr</span><span class="sxs-lookup"><span data-stu-id="a3cdc-102">CorEventAttr Enumeration</span></span>
<span data-ttu-id="a3cdc-103">Contiene valori che descrivono i metadati di un evento.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-103">Contains values that describe the metadata of an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3cdc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a3cdc-104">Syntax</span></span>  
  
```cpp  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="a3cdc-105">Members</span><span class="sxs-lookup"><span data-stu-id="a3cdc-105">Members</span></span>  
  
|<span data-ttu-id="a3cdc-106">Membro</span><span class="sxs-lookup"><span data-stu-id="a3cdc-106">Member</span></span>|<span data-ttu-id="a3cdc-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a3cdc-107">Description</span></span>|  
|------------|-----------------|  
|`evSpecialName`|<span data-ttu-id="a3cdc-108">Specifica che l'evento è speciale e che il nome descrive come.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-108">Specifies that the event is special, and that its name describes how.</span></span>|  
|`evReservedMask`|<span data-ttu-id="a3cdc-109">Riservato per uso interno da parte del Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-109">Reserved for internal use by the common language runtime.</span></span>|  
|`evRTSpecialName`|<span data-ttu-id="a3cdc-110">Specifica che il Common Language Runtime deve controllare la codifica del nome dell'evento.</span><span class="sxs-lookup"><span data-stu-id="a3cdc-110">Specifies that the common language runtime should check the encoding of the event name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a3cdc-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a3cdc-111">Requirements</span></span>  
 <span data-ttu-id="a3cdc-112">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3cdc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3cdc-113">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="a3cdc-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="a3cdc-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3cdc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3cdc-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3cdc-115">See also</span></span>

- [<span data-ttu-id="a3cdc-116">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="a3cdc-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

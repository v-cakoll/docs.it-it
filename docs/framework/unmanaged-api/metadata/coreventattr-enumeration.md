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
ms.openlocfilehash: e22b390271a7813dd1d34aecf5f8a62d7eb81005
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007437"
---
# <a name="coreventattr-enumeration"></a><span data-ttu-id="c2c9c-102">Enumerazione CorEventAttr</span><span class="sxs-lookup"><span data-stu-id="c2c9c-102">CorEventAttr Enumeration</span></span>
<span data-ttu-id="c2c9c-103">Contiene valori che descrivono i metadati di un evento.</span><span class="sxs-lookup"><span data-stu-id="c2c9c-103">Contains values that describe the metadata of an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2c9c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c2c9c-104">Syntax</span></span>  
  
```cpp  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="c2c9c-105">Membri</span><span class="sxs-lookup"><span data-stu-id="c2c9c-105">Members</span></span>  
  
|<span data-ttu-id="c2c9c-106">Membro</span><span class="sxs-lookup"><span data-stu-id="c2c9c-106">Member</span></span>|<span data-ttu-id="c2c9c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c2c9c-107">Description</span></span>|  
|------------|-----------------|  
|`evSpecialName`|<span data-ttu-id="c2c9c-108">Specifica che l'evento è speciale e che il nome descrive come.</span><span class="sxs-lookup"><span data-stu-id="c2c9c-108">Specifies that the event is special, and that its name describes how.</span></span>|  
|`evReservedMask`|<span data-ttu-id="c2c9c-109">Riservato per uso interno da parte del Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="c2c9c-109">Reserved for internal use by the common language runtime.</span></span>|  
|`evRTSpecialName`|<span data-ttu-id="c2c9c-110">Specifica che il Common Language Runtime deve controllare la codifica del nome dell'evento.</span><span class="sxs-lookup"><span data-stu-id="c2c9c-110">Specifies that the common language runtime should check the encoding of the event name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c2c9c-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c2c9c-111">Requirements</span></span>  
 <span data-ttu-id="c2c9c-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2c9c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2c9c-113">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="c2c9c-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c2c9c-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2c9c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2c9c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2c9c-115">See also</span></span>

- [<span data-ttu-id="c2c9c-116">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="c2c9c-116">Metadata Enumerations</span></span>](metadata-enumerations.md)

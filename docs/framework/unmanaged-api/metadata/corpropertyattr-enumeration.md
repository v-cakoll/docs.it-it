---
title: Enumerazione CorPropertyAttr
ms.date: 03/30/2017
api_name:
- CorPropertyAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPropertyAttr
helpviewer_keywords:
- CorPropertyAttr enumeration [.NET Framework metadata]
ms.assetid: 58ac8202-854d-4efd-acfb-d2da8b446e12
topic_type:
- apiref
ms.openlocfilehash: 95a798d662b44cf2e088af84d3b1eec97da8e7fb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177948"
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="87804-102">Enumerazione CorPropertyAttr</span><span class="sxs-lookup"><span data-stu-id="87804-102">CorPropertyAttr Enumeration</span></span>
<span data-ttu-id="87804-103">Contiene valori che descrivono i metadati di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="87804-103">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87804-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="87804-104">Syntax</span></span>  
  
```cpp  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="87804-105">Members</span><span class="sxs-lookup"><span data-stu-id="87804-105">Members</span></span>  
  
|<span data-ttu-id="87804-106">Membro</span><span class="sxs-lookup"><span data-stu-id="87804-106">Member</span></span>|<span data-ttu-id="87804-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="87804-107">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="87804-108">Specifica che la proprietà è speciale e che il nome descrive how.</span><span class="sxs-lookup"><span data-stu-id="87804-108">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="87804-109">Riservato per uso interno da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="87804-109">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="87804-110">Specifica che le API interne dei metadati di Common Language Runtime devono controllare la codifica del nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="87804-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="87804-111">Specifica che la proprietà ha un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="87804-111">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="87804-112">Non utilizzato.</span><span class="sxs-lookup"><span data-stu-id="87804-112">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="87804-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="87804-113">Requirements</span></span>  
 <span data-ttu-id="87804-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87804-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87804-115">**Intestazione:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="87804-115">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="87804-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87804-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87804-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87804-117">See also</span></span>

- [<span data-ttu-id="87804-118">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="87804-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

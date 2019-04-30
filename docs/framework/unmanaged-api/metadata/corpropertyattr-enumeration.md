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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f1a0fff266e964b506b2dc7c4030caa54abaa5ed
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045370"
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="0e3db-102">Enumerazione CorPropertyAttr</span><span class="sxs-lookup"><span data-stu-id="0e3db-102">CorPropertyAttr Enumeration</span></span>
<span data-ttu-id="0e3db-103">Contiene valori che descrivono i metadati di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="0e3db-103">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e3db-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0e3db-104">Syntax</span></span>  
  
```  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,   
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="0e3db-105">Membri</span><span class="sxs-lookup"><span data-stu-id="0e3db-105">Members</span></span>  
  
|<span data-ttu-id="0e3db-106">Member</span><span class="sxs-lookup"><span data-stu-id="0e3db-106">Member</span></span>|<span data-ttu-id="0e3db-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0e3db-107">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="0e3db-108">Specifica che la proprietà è speciale e che il relativo nome viene descritto come.</span><span class="sxs-lookup"><span data-stu-id="0e3db-108">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="0e3db-109">Riservato per uso interno da common language runtime.</span><span class="sxs-lookup"><span data-stu-id="0e3db-109">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="0e3db-110">Specifica che i metadati di common language runtime le API interne devono verificare la codifica del nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="0e3db-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="0e3db-111">Specifica che la proprietà ha un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="0e3db-111">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="0e3db-112">Non usato.</span><span class="sxs-lookup"><span data-stu-id="0e3db-112">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0e3db-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0e3db-113">Requirements</span></span>  
 <span data-ttu-id="0e3db-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e3db-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e3db-115">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="0e3db-115">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="0e3db-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e3db-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e3db-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e3db-117">See also</span></span>

- [<span data-ttu-id="0e3db-118">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="0e3db-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

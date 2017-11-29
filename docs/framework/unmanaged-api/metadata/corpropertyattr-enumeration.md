---
title: Enumerazione CorPropertyAttr
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorPropertyAttr
api_location: mscoree.dll
api_type: COM
f1_keywords: CorPropertyAttr
helpviewer_keywords: CorPropertyAttr enumeration [.NET Framework metadata]
ms.assetid: 58ac8202-854d-4efd-acfb-d2da8b446e12
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a87676064f39dc01d04e881bbf46476fb12a1c65
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="2b83a-102">Enumerazione CorPropertyAttr</span><span class="sxs-lookup"><span data-stu-id="2b83a-102">CorPropertyAttr Enumeration</span></span>
<span data-ttu-id="2b83a-103">Contiene valori che descrivono i metadati di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="2b83a-103">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b83a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2b83a-104">Syntax</span></span>  
  
```  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,   
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="2b83a-105">Membri</span><span class="sxs-lookup"><span data-stu-id="2b83a-105">Members</span></span>  
  
|<span data-ttu-id="2b83a-106">Membro</span><span class="sxs-lookup"><span data-stu-id="2b83a-106">Member</span></span>|<span data-ttu-id="2b83a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b83a-107">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="2b83a-108">Specifica che la proprietà è speciale e che il relativo nome viene descritto come.</span><span class="sxs-lookup"><span data-stu-id="2b83a-108">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="2b83a-109">Riservato per uso interno da common language runtime.</span><span class="sxs-lookup"><span data-stu-id="2b83a-109">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="2b83a-110">Specifica che i metadati di common language runtime API interne devono verificare la codifica del nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="2b83a-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="2b83a-111">Specifica che la proprietà ha un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="2b83a-111">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="2b83a-112">Non usato.</span><span class="sxs-lookup"><span data-stu-id="2b83a-112">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2b83a-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2b83a-113">Requirements</span></span>  
 <span data-ttu-id="2b83a-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b83a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b83a-115">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="2b83a-115">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="2b83a-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b83a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b83a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b83a-117">See Also</span></span>  
 [<span data-ttu-id="2b83a-118">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="2b83a-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

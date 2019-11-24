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
ms.openlocfilehash: 2d49a146a465210cea8466a75666ca3f800b090b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450137"
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="32e4e-102">Enumerazione CorPropertyAttr</span><span class="sxs-lookup"><span data-stu-id="32e4e-102">CorPropertyAttr Enumeration</span></span>
<span data-ttu-id="32e4e-103">Contiene valori che descrivono i metadati di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="32e4e-103">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32e4e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="32e4e-104">Syntax</span></span>  
  
```cpp  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,   
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="32e4e-105">Members</span><span class="sxs-lookup"><span data-stu-id="32e4e-105">Members</span></span>  
  
|<span data-ttu-id="32e4e-106">Member</span><span class="sxs-lookup"><span data-stu-id="32e4e-106">Member</span></span>|<span data-ttu-id="32e4e-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="32e4e-107">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="32e4e-108">Specifies that the property is special, and that its name describes how.</span><span class="sxs-lookup"><span data-stu-id="32e4e-108">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="32e4e-109">Reserved for internal use by the common language runtime.</span><span class="sxs-lookup"><span data-stu-id="32e4e-109">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="32e4e-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span><span class="sxs-lookup"><span data-stu-id="32e4e-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="32e4e-111">Specifies that the property has a default value.</span><span class="sxs-lookup"><span data-stu-id="32e4e-111">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="32e4e-112">Non usato.</span><span class="sxs-lookup"><span data-stu-id="32e4e-112">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="32e4e-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="32e4e-113">Requirements</span></span>  
 <span data-ttu-id="32e4e-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32e4e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32e4e-115">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="32e4e-115">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="32e4e-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32e4e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32e4e-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32e4e-117">See also</span></span>

- [<span data-ttu-id="32e4e-118">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="32e4e-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

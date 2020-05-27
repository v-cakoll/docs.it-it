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
ms.openlocfilehash: b6651f30e0df3a5ffc29d310b9067e76761dcf01
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007533"
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="f3201-102">Enumerazione CorPropertyAttr</span><span class="sxs-lookup"><span data-stu-id="f3201-102">CorPropertyAttr Enumeration</span></span>
<span data-ttu-id="f3201-103">Contiene valori che descrivono i metadati di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="f3201-103">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3201-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f3201-104">Syntax</span></span>  
  
```cpp  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="f3201-105">Membri</span><span class="sxs-lookup"><span data-stu-id="f3201-105">Members</span></span>  
  
|<span data-ttu-id="f3201-106">Membro</span><span class="sxs-lookup"><span data-stu-id="f3201-106">Member</span></span>|<span data-ttu-id="f3201-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f3201-107">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="f3201-108">Specifica che la proprietà è speciale e che il nome descrive come.</span><span class="sxs-lookup"><span data-stu-id="f3201-108">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="f3201-109">Riservato per uso interno da parte del Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="f3201-109">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="f3201-110">Specifica che le API interne dei metadati di Common Language Runtime devono verificare la codifica del nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="f3201-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="f3201-111">Specifica che la proprietà ha un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="f3201-111">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="f3201-112">Non utilizzato.</span><span class="sxs-lookup"><span data-stu-id="f3201-112">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f3201-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f3201-113">Requirements</span></span>  
 <span data-ttu-id="f3201-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3201-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3201-115">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="f3201-115">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="f3201-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3201-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3201-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3201-117">See also</span></span>

- [<span data-ttu-id="f3201-118">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="f3201-118">Metadata Enumerations</span></span>](metadata-enumerations.md)

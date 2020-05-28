---
title: Enumerazione CorImportOptions
ms.date: 03/30/2017
api_name:
- CorImportOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorImportOptions
helpviewer_keywords:
- CorImportOptions enumeration [.NET Framework metadata]
ms.assetid: 4e5d03cb-97c9-4ff4-8dbd-17d94ee374d3
topic_type:
- apiref
ms.openlocfilehash: 3be8a004be752af8a8675a3499bdb6cbfd785840
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009197"
---
# <a name="corimportoptions-enumeration"></a><span data-ttu-id="6301f-102">Enumerazione CorImportOptions</span><span class="sxs-lookup"><span data-stu-id="6301f-102">CorImportOptions Enumeration</span></span>
<span data-ttu-id="6301f-103">Contiene valori di flag che controllano il comportamento durante l'importazione di un assembly esterno all'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="6301f-103">Contains flag values that control the behavior during importation of an assembly outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6301f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6301f-104">Syntax</span></span>  
  
```cpp  
typedef enum CorImportOptions {  
  
    MDImportOptionDefault                = 0x00000000,  
    MDImportOptionAll                    = 0xFFFFFFFF,  
    MDImportOptionAllTypeDefs            = 0x00000001,  
    MDImportOptionAllMethodDefs          = 0x00000002,  
    MDImportOptionAllFieldDefs           = 0x00000004,  
    MDImportOptionAllProperties          = 0x00000008,  
    MDImportOptionAllEvents              = 0x00000010,  
    MDImportOptionAllCustomAttributes    = 0x00000020,  
    MDImportOptionAllExportedTypes       = 0x00000040  
  
} CorImportOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="6301f-105">Membri</span><span class="sxs-lookup"><span data-stu-id="6301f-105">Members</span></span>  
  
|<span data-ttu-id="6301f-106">Membro</span><span class="sxs-lookup"><span data-stu-id="6301f-106">Member</span></span>|<span data-ttu-id="6301f-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6301f-107">Description</span></span>|  
|------------|-----------------|  
|`MDImportOptionDefault`|<span data-ttu-id="6301f-108">Indica il comportamento predefinito, ovvero ignorare i record eliminati.</span><span class="sxs-lookup"><span data-stu-id="6301f-108">Indicates the default behavior, which is to skip deleted records.</span></span>|  
|`MDImportOptionAll`|<span data-ttu-id="6301f-109">Indica che tutti i metadati devono essere enumerati.</span><span class="sxs-lookup"><span data-stu-id="6301f-109">Indicates that all metadata should be enumerated.</span></span>|  
|`MDImportOptionAllTypeDefs`|<span data-ttu-id="6301f-110">Indica che devono essere enumerati tutti i TypeDef, inclusi quelli eliminati.</span><span class="sxs-lookup"><span data-stu-id="6301f-110">Indicates that all TypeDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllMethodDefs`|<span data-ttu-id="6301f-111">Indica che devono essere enumerati tutti MethodDefs, inclusi quelli eliminati.</span><span class="sxs-lookup"><span data-stu-id="6301f-111">Indicates that all MethodDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllFieldDefs`|<span data-ttu-id="6301f-112">Indica che devono essere enumerati tutti FieldDefs, inclusi quelli eliminati.</span><span class="sxs-lookup"><span data-stu-id="6301f-112">Indicates that all FieldDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllProperties`|<span data-ttu-id="6301f-113">Indica che devono essere enumerati tutti PropertyDefs, inclusi quelli eliminati.</span><span class="sxs-lookup"><span data-stu-id="6301f-113">Indicates that all PropertyDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllEvents`|<span data-ttu-id="6301f-114">Indica che devono essere enumerati tutti EventDefs, inclusi quelli eliminati.</span><span class="sxs-lookup"><span data-stu-id="6301f-114">Indicates that all EventDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllCustomAttributes`|<span data-ttu-id="6301f-115">Indica che tutti gli attributi personalizzati, inclusi quelli eliminati, devono essere enumerati.</span><span class="sxs-lookup"><span data-stu-id="6301f-115">Indicates that all custom attributes, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllExportedTypes`|<span data-ttu-id="6301f-116">Indica che tutti i tipi esportati, inclusi quelli eliminati, devono essere enumerati.</span><span class="sxs-lookup"><span data-stu-id="6301f-116">Indicates that all exported types, including deleted ones, should be enumerated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6301f-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6301f-117">Requirements</span></span>  
 <span data-ttu-id="6301f-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6301f-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6301f-119">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="6301f-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="6301f-120">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6301f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6301f-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6301f-121">See also</span></span>

- [<span data-ttu-id="6301f-122">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="6301f-122">Metadata Enumerations</span></span>](metadata-enumerations.md)

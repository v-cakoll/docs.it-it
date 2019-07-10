---
title: Struttura COR_FIELD_OFFSET
ms.date: 03/30/2017
api_name:
- COR_FIELD_OFFSET
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_FIELD_OFFSET
helpviewer_keywords:
- COR_FIELD_OFFSET structure [.NET Framework metadata]
ms.assetid: cced5298-277f-4a5a-8ecf-a0050c1096ea
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fdfbb22d231d16be7757ff5df26a5a010928af54
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767057"
---
# <a name="corfieldoffset-structure"></a><span data-ttu-id="b5a9f-102">Struttura COR_FIELD_OFFSET</span><span class="sxs-lookup"><span data-stu-id="b5a9f-102">COR_FIELD_OFFSET Structure</span></span>
<span data-ttu-id="b5a9f-103">Archivia l'offset del campo specificato all'interno di una classe.</span><span class="sxs-lookup"><span data-stu-id="b5a9f-103">Stores the offset, within a class, of the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5a9f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b5a9f-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_FIELD_OFFSET {  
    mdFieldDef  ridOfField;  
    ULONG       ulOffset;  
} COR_FIELD_OFFSET;  
```  
  
## <a name="members"></a><span data-ttu-id="b5a9f-105">Membri</span><span class="sxs-lookup"><span data-stu-id="b5a9f-105">Members</span></span>  
  
|<span data-ttu-id="b5a9f-106">Member</span><span class="sxs-lookup"><span data-stu-id="b5a9f-106">Member</span></span>|<span data-ttu-id="b5a9f-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b5a9f-107">Description</span></span>|  
|------------|-----------------|  
|`ridOfField`|<span data-ttu-id="b5a9f-108">Un `mdFieldDef` token di metadati che rappresenta il campo.</span><span class="sxs-lookup"><span data-stu-id="b5a9f-108">An `mdFieldDef` metadata token that represents the field.</span></span>|  
|`ulOffset`|<span data-ttu-id="b5a9f-109">Offset del campo nella relativa classe.</span><span class="sxs-lookup"><span data-stu-id="b5a9f-109">The field's offset within its class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5a9f-110">Note</span><span class="sxs-lookup"><span data-stu-id="b5a9f-110">Remarks</span></span>  
 <span data-ttu-id="b5a9f-111">[IMetaDataImport:: GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md) e [SetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md) metodi accettano un parametro di tipo `COR_FIELD_OFFSET`.</span><span class="sxs-lookup"><span data-stu-id="b5a9f-111">[IMetaDataImport::GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md) and [IMetaDataEmit::SetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md) methods take a parameter of type `COR_FIELD_OFFSET`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5a9f-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b5a9f-112">Requirements</span></span>  
 <span data-ttu-id="b5a9f-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5a9f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5a9f-114">**Intestazione:** CorHdr. H, Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="b5a9f-114">**Header:** CorHdr.h, CorProf.idl</span></span>  
  
 <span data-ttu-id="b5a9f-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5a9f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5a9f-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5a9f-116">See also</span></span>

- [<span data-ttu-id="b5a9f-117">Strutture di metadati</span><span class="sxs-lookup"><span data-stu-id="b5a9f-117">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="b5a9f-118">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="b5a9f-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="b5a9f-119">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="b5a9f-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)

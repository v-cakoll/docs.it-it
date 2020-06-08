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
ms.openlocfilehash: 8cc803e3cf1442d324bf2eed0a37d0d236acd86d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493058"
---
# <a name="cor_field_offset-structure"></a><span data-ttu-id="356b1-102">Struttura COR_FIELD_OFFSET</span><span class="sxs-lookup"><span data-stu-id="356b1-102">COR_FIELD_OFFSET Structure</span></span>
<span data-ttu-id="356b1-103">Archivia l'offset del campo specificato all'interno di una classe.</span><span class="sxs-lookup"><span data-stu-id="356b1-103">Stores the offset, within a class, of the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="356b1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="356b1-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_FIELD_OFFSET {  
    mdFieldDef  ridOfField;  
    ULONG       ulOffset;  
} COR_FIELD_OFFSET;  
```  
  
## <a name="members"></a><span data-ttu-id="356b1-105">Membri</span><span class="sxs-lookup"><span data-stu-id="356b1-105">Members</span></span>  
  
|<span data-ttu-id="356b1-106">Membro</span><span class="sxs-lookup"><span data-stu-id="356b1-106">Member</span></span>|<span data-ttu-id="356b1-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="356b1-107">Description</span></span>|  
|------------|-----------------|  
|`ridOfField`|<span data-ttu-id="356b1-108">`mdFieldDef`Token di metadati che rappresenta il campo.</span><span class="sxs-lookup"><span data-stu-id="356b1-108">An `mdFieldDef` metadata token that represents the field.</span></span>|  
|`ulOffset`|<span data-ttu-id="356b1-109">Offset del campo all'interno della relativa classe.</span><span class="sxs-lookup"><span data-stu-id="356b1-109">The field's offset within its class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="356b1-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="356b1-110">Remarks</span></span>  
 <span data-ttu-id="356b1-111">I metodi [IMetaDataImport:: GetClassLayout](imetadataimport-getclasslayout-method.md) e [IMetaDataEmit:: SetClassLayout](imetadataemit-setclasslayout-method.md) accettano un parametro di tipo `COR_FIELD_OFFSET` .</span><span class="sxs-lookup"><span data-stu-id="356b1-111">[IMetaDataImport::GetClassLayout](imetadataimport-getclasslayout-method.md) and [IMetaDataEmit::SetClassLayout](imetadataemit-setclasslayout-method.md) methods take a parameter of type `COR_FIELD_OFFSET`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="356b1-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="356b1-112">Requirements</span></span>  
 <span data-ttu-id="356b1-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="356b1-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="356b1-114">**Intestazione:** CorHdr. h, CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="356b1-114">**Header:** CorHdr.h, CorProf.idl</span></span>  
  
 <span data-ttu-id="356b1-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="356b1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="356b1-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="356b1-116">See also</span></span>

- [<span data-ttu-id="356b1-117">Strutture di metadati</span><span class="sxs-lookup"><span data-stu-id="356b1-117">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="356b1-118">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="356b1-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="356b1-119">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="356b1-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)

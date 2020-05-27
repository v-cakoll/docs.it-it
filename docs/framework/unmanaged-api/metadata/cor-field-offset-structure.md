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
ms.openlocfilehash: 70fb637cd1edf81be140b0e3306e3b0a483653a6
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007988"
---
# <a name="cor_field_offset-structure"></a><span data-ttu-id="1a637-102">Struttura COR_FIELD_OFFSET</span><span class="sxs-lookup"><span data-stu-id="1a637-102">COR_FIELD_OFFSET Structure</span></span>
<span data-ttu-id="1a637-103">Archivia l'offset del campo specificato all'interno di una classe.</span><span class="sxs-lookup"><span data-stu-id="1a637-103">Stores the offset, within a class, of the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a637-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1a637-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_FIELD_OFFSET {  
    mdFieldDef  ridOfField;  
    ULONG       ulOffset;  
} COR_FIELD_OFFSET;  
```  
  
## <a name="members"></a><span data-ttu-id="1a637-105">Membri</span><span class="sxs-lookup"><span data-stu-id="1a637-105">Members</span></span>  
  
|<span data-ttu-id="1a637-106">Membro</span><span class="sxs-lookup"><span data-stu-id="1a637-106">Member</span></span>|<span data-ttu-id="1a637-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1a637-107">Description</span></span>|  
|------------|-----------------|  
|`ridOfField`|<span data-ttu-id="1a637-108">`mdFieldDef`Token di metadati che rappresenta il campo.</span><span class="sxs-lookup"><span data-stu-id="1a637-108">An `mdFieldDef` metadata token that represents the field.</span></span>|  
|`ulOffset`|<span data-ttu-id="1a637-109">Offset del campo all'interno della relativa classe.</span><span class="sxs-lookup"><span data-stu-id="1a637-109">The field's offset within its class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a637-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="1a637-110">Remarks</span></span>  
 <span data-ttu-id="1a637-111">I metodi [IMetaDataImport:: GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md) e [IMetaDataEmit:: SetClassLayout](imetadataemit-setclasslayout-method.md) accettano un parametro di tipo `COR_FIELD_OFFSET` .</span><span class="sxs-lookup"><span data-stu-id="1a637-111">[IMetaDataImport::GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md) and [IMetaDataEmit::SetClassLayout](imetadataemit-setclasslayout-method.md) methods take a parameter of type `COR_FIELD_OFFSET`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a637-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1a637-112">Requirements</span></span>  
 <span data-ttu-id="1a637-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a637-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a637-114">**Intestazione:** CorHdr. h, CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="1a637-114">**Header:** CorHdr.h, CorProf.idl</span></span>  
  
 <span data-ttu-id="1a637-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a637-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a637-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a637-116">See also</span></span>

- [<span data-ttu-id="1a637-117">Strutture di metadati</span><span class="sxs-lookup"><span data-stu-id="1a637-117">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="1a637-118">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="1a637-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="1a637-119">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="1a637-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)

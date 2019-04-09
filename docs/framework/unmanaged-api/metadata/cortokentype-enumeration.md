---
title: Enumerazione CorTokenType
ms.date: 03/30/2017
api_name:
- CorTokenType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorTokenType
helpviewer_keywords:
- CorTokenType enumeration [.NET Framework metadata]
ms.assetid: 93c9a369-225f-4eff-9b78-3fbee4902cf1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1b33b50e53c454f2b62253d12943ea044240d8cc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230512"
---
# <a name="cortokentype-enumeration"></a><span data-ttu-id="54593-102">Enumerazione CorTokenType</span><span class="sxs-lookup"><span data-stu-id="54593-102">CorTokenType Enumeration</span></span>
<span data-ttu-id="54593-103">Indica il tipo di un token di metadati.</span><span class="sxs-lookup"><span data-stu-id="54593-103">Indicates the type of a metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54593-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="54593-104">Syntax</span></span>  
  
```  
typedef enum CorTokenType {  
  
    mdtModule                       = 0x00000000,  
    mdtTypeRef                      = 0x01000000,  
    mdtTypeDef                      = 0x02000000,  
    mdtFieldDef                     = 0x04000000,  
    mdtMethodDef                    = 0x06000000,  
    mdtParamDef                     = 0x08000000,  
    mdtInterfaceImpl                = 0x09000000,  
    mdtMemberRef                    = 0x0a000000,  
    mdtCustomAttribute              = 0x0c000000,  
    mdtPermission                   = 0x0e000000,  
    mdtSignature                    = 0x11000000,  
    mdtEvent                        = 0x14000000,  
    mdtProperty                     = 0x17000000,  
    mdtModuleRef                    = 0x1a000000,  
    mdtTypeSpec                     = 0x1b000000,  
    mdtAssembly                     = 0x20000000,  
    mdtAssemblyRef                  = 0x23000000,  
    mdtFile                         = 0x26000000,  
    mdtExportedType                 = 0x27000000,  
    mdtManifestResource             = 0x28000000,  
    mdtGenericParam                 = 0x2a000000,  
    mdtMethodSpec                   = 0x2b000000,  
    mdtGenericParamConstraint       = 0x2c000000,  
    mdtString                       = 0x70000000,  
    mdtName                         = 0x71000000,  
    mdtBaseType                     = 0x72000000  
  
} CorTokenType;  
```  
  
## <a name="members"></a><span data-ttu-id="54593-105">Membri</span><span class="sxs-lookup"><span data-stu-id="54593-105">Members</span></span>  
  
|<span data-ttu-id="54593-106">Member</span><span class="sxs-lookup"><span data-stu-id="54593-106">Member</span></span>|<span data-ttu-id="54593-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="54593-107">Description</span></span>|  
|------------|-----------------|  
|`mdtModule`|<span data-ttu-id="54593-108">Un `mdModule` token.</span><span class="sxs-lookup"><span data-stu-id="54593-108">An `mdModule` token.</span></span>|  
|`mdtTypeRef`|<span data-ttu-id="54593-109">Un `mdTypeRef` token.</span><span class="sxs-lookup"><span data-stu-id="54593-109">An `mdTypeRef` token.</span></span>|  
|`mdtTypeDef`|<span data-ttu-id="54593-110">Un `mdTypeDef` token.</span><span class="sxs-lookup"><span data-stu-id="54593-110">An `mdTypeDef` token.</span></span>|  
|`mdtFieldDef`|<span data-ttu-id="54593-111">Un `mdFieldDef` token.</span><span class="sxs-lookup"><span data-stu-id="54593-111">An `mdFieldDef` token.</span></span>|  
|`mdtMethodDef`|<span data-ttu-id="54593-112">Un `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="54593-112">An `mdMethodDef` token.</span></span>|  
|`mdtParamDef`|<span data-ttu-id="54593-113">Un `mdParamDef` token.</span><span class="sxs-lookup"><span data-stu-id="54593-113">An `mdParamDef` token.</span></span>|  
|`mdtInterfaceImpl`|<span data-ttu-id="54593-114">Un `mdInterfaceImpl` token.</span><span class="sxs-lookup"><span data-stu-id="54593-114">An `mdInterfaceImpl` token.</span></span>|  
|`mdtMemberRef`|<span data-ttu-id="54593-115">Un `mdMemberRef` token.</span><span class="sxs-lookup"><span data-stu-id="54593-115">An `mdMemberRef` token.</span></span>|  
|`mdtCustomAttribute`|<span data-ttu-id="54593-116">Un `mdCustomAttribute` token.</span><span class="sxs-lookup"><span data-stu-id="54593-116">An `mdCustomAttribute` token.</span></span>|  
|`mdtPermission`|<span data-ttu-id="54593-117">Un `mdPermission` token.</span><span class="sxs-lookup"><span data-stu-id="54593-117">An `mdPermission` token.</span></span>|  
|`mdtSignature`|<span data-ttu-id="54593-118">Un `mdSignature` token.</span><span class="sxs-lookup"><span data-stu-id="54593-118">An `mdSignature` token.</span></span>|  
|`mdtEvent`|<span data-ttu-id="54593-119">Un `mdEvent` token.</span><span class="sxs-lookup"><span data-stu-id="54593-119">An `mdEvent` token.</span></span>|  
|`mdtProperty`|<span data-ttu-id="54593-120">Un `mdProperty` token.</span><span class="sxs-lookup"><span data-stu-id="54593-120">An `mdProperty` token.</span></span>|  
|`mdtModuleRef`|<span data-ttu-id="54593-121">Un `mdModuleRef` token.</span><span class="sxs-lookup"><span data-stu-id="54593-121">An `mdModuleRef` token.</span></span>|  
|`mdtTypeSpec`|<span data-ttu-id="54593-122">Un `mdTypeSpec` token.</span><span class="sxs-lookup"><span data-stu-id="54593-122">An `mdTypeSpec` token.</span></span>|  
|`mdtAssembly`|<span data-ttu-id="54593-123">Un `mdAssembly` token.</span><span class="sxs-lookup"><span data-stu-id="54593-123">An `mdAssembly` token.</span></span>|  
|`mdtAssemblyRef`|<span data-ttu-id="54593-124">Un `mdAssemblyRef` token.</span><span class="sxs-lookup"><span data-stu-id="54593-124">An `mdAssemblyRef` token.</span></span>|  
|`mdtFile`|<span data-ttu-id="54593-125">Un `mdFile` token.</span><span class="sxs-lookup"><span data-stu-id="54593-125">An `mdFile` token.</span></span>|  
|`mdtExportedType`|<span data-ttu-id="54593-126">Un `mdExportedType` token.</span><span class="sxs-lookup"><span data-stu-id="54593-126">An `mdExportedType` token.</span></span>|  
|`mdtManifestResource`|<span data-ttu-id="54593-127">Un `mdManifestResource` token.</span><span class="sxs-lookup"><span data-stu-id="54593-127">An `mdManifestResource` token.</span></span>|  
|`mdtGenericParam`|<span data-ttu-id="54593-128">Un `mdGenericParam` token.</span><span class="sxs-lookup"><span data-stu-id="54593-128">An `mdGenericParam` token.</span></span>|  
|`mdtMethodSpec`|<span data-ttu-id="54593-129">Un `mdMethodSpec` token.</span><span class="sxs-lookup"><span data-stu-id="54593-129">An `mdMethodSpec` token.</span></span>|  
|`mdtGenericParamConstraint`|<span data-ttu-id="54593-130">Un `mdGenericParamConstraint` token.</span><span class="sxs-lookup"><span data-stu-id="54593-130">An `mdGenericParamConstraint` token.</span></span>|  
|`mdtString`|<span data-ttu-id="54593-131">Un `mdString` token.</span><span class="sxs-lookup"><span data-stu-id="54593-131">An `mdString` token.</span></span>|  
|`mdtName`|<span data-ttu-id="54593-132">Un `mdName` token.</span><span class="sxs-lookup"><span data-stu-id="54593-132">An `mdName` token.</span></span>|  
|`mdtBaseType`|<span data-ttu-id="54593-133">Non usato.</span><span class="sxs-lookup"><span data-stu-id="54593-133">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54593-134">Note</span><span class="sxs-lookup"><span data-stu-id="54593-134">Remarks</span></span>  
 <span data-ttu-id="54593-135">Ogni valore è uguale al valore del byte alto nel token di metadati corrispondente.</span><span class="sxs-lookup"><span data-stu-id="54593-135">Each value is equal to the value of the top byte in the corresponding metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54593-136">Requisiti</span><span class="sxs-lookup"><span data-stu-id="54593-136">Requirements</span></span>  
 <span data-ttu-id="54593-137">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54593-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54593-138">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="54593-138">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="54593-139">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="54593-139">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="54593-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54593-140">See also</span></span>

- [<span data-ttu-id="54593-141">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="54593-141">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

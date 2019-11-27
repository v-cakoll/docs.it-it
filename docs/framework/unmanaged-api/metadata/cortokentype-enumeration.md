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
ms.openlocfilehash: 74807a678b5c0c2738f33fe552f6462af93ca1f9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436461"
---
# <a name="cortokentype-enumeration"></a><span data-ttu-id="62952-102">Enumerazione CorTokenType</span><span class="sxs-lookup"><span data-stu-id="62952-102">CorTokenType Enumeration</span></span>
<span data-ttu-id="62952-103">Indica il tipo di token di metadati.</span><span class="sxs-lookup"><span data-stu-id="62952-103">Indicates the type of a metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62952-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="62952-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="62952-105">Members</span><span class="sxs-lookup"><span data-stu-id="62952-105">Members</span></span>  
  
|<span data-ttu-id="62952-106">Membro</span><span class="sxs-lookup"><span data-stu-id="62952-106">Member</span></span>|<span data-ttu-id="62952-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="62952-107">Description</span></span>|  
|------------|-----------------|  
|`mdtModule`|<span data-ttu-id="62952-108">Token `mdModule`.</span><span class="sxs-lookup"><span data-stu-id="62952-108">An `mdModule` token.</span></span>|  
|`mdtTypeRef`|<span data-ttu-id="62952-109">Token `mdTypeRef`.</span><span class="sxs-lookup"><span data-stu-id="62952-109">An `mdTypeRef` token.</span></span>|  
|`mdtTypeDef`|<span data-ttu-id="62952-110">Token `mdTypeDef`.</span><span class="sxs-lookup"><span data-stu-id="62952-110">An `mdTypeDef` token.</span></span>|  
|`mdtFieldDef`|<span data-ttu-id="62952-111">Token `mdFieldDef`.</span><span class="sxs-lookup"><span data-stu-id="62952-111">An `mdFieldDef` token.</span></span>|  
|`mdtMethodDef`|<span data-ttu-id="62952-112">Token `mdMethodDef`.</span><span class="sxs-lookup"><span data-stu-id="62952-112">An `mdMethodDef` token.</span></span>|  
|`mdtParamDef`|<span data-ttu-id="62952-113">Token `mdParamDef`.</span><span class="sxs-lookup"><span data-stu-id="62952-113">An `mdParamDef` token.</span></span>|  
|`mdtInterfaceImpl`|<span data-ttu-id="62952-114">Token `mdInterfaceImpl`.</span><span class="sxs-lookup"><span data-stu-id="62952-114">An `mdInterfaceImpl` token.</span></span>|  
|`mdtMemberRef`|<span data-ttu-id="62952-115">Token `mdMemberRef`.</span><span class="sxs-lookup"><span data-stu-id="62952-115">An `mdMemberRef` token.</span></span>|  
|`mdtCustomAttribute`|<span data-ttu-id="62952-116">Token `mdCustomAttribute`.</span><span class="sxs-lookup"><span data-stu-id="62952-116">An `mdCustomAttribute` token.</span></span>|  
|`mdtPermission`|<span data-ttu-id="62952-117">Token `mdPermission`.</span><span class="sxs-lookup"><span data-stu-id="62952-117">An `mdPermission` token.</span></span>|  
|`mdtSignature`|<span data-ttu-id="62952-118">Token `mdSignature`.</span><span class="sxs-lookup"><span data-stu-id="62952-118">An `mdSignature` token.</span></span>|  
|`mdtEvent`|<span data-ttu-id="62952-119">Token `mdEvent`.</span><span class="sxs-lookup"><span data-stu-id="62952-119">An `mdEvent` token.</span></span>|  
|`mdtProperty`|<span data-ttu-id="62952-120">Token `mdProperty`.</span><span class="sxs-lookup"><span data-stu-id="62952-120">An `mdProperty` token.</span></span>|  
|`mdtModuleRef`|<span data-ttu-id="62952-121">Token `mdModuleRef`.</span><span class="sxs-lookup"><span data-stu-id="62952-121">An `mdModuleRef` token.</span></span>|  
|`mdtTypeSpec`|<span data-ttu-id="62952-122">Token `mdTypeSpec`.</span><span class="sxs-lookup"><span data-stu-id="62952-122">An `mdTypeSpec` token.</span></span>|  
|`mdtAssembly`|<span data-ttu-id="62952-123">Token `mdAssembly`.</span><span class="sxs-lookup"><span data-stu-id="62952-123">An `mdAssembly` token.</span></span>|  
|`mdtAssemblyRef`|<span data-ttu-id="62952-124">Token `mdAssemblyRef`.</span><span class="sxs-lookup"><span data-stu-id="62952-124">An `mdAssemblyRef` token.</span></span>|  
|`mdtFile`|<span data-ttu-id="62952-125">Token `mdFile`.</span><span class="sxs-lookup"><span data-stu-id="62952-125">An `mdFile` token.</span></span>|  
|`mdtExportedType`|<span data-ttu-id="62952-126">Token `mdExportedType`.</span><span class="sxs-lookup"><span data-stu-id="62952-126">An `mdExportedType` token.</span></span>|  
|`mdtManifestResource`|<span data-ttu-id="62952-127">Token `mdManifestResource`.</span><span class="sxs-lookup"><span data-stu-id="62952-127">An `mdManifestResource` token.</span></span>|  
|`mdtGenericParam`|<span data-ttu-id="62952-128">Token `mdGenericParam`.</span><span class="sxs-lookup"><span data-stu-id="62952-128">An `mdGenericParam` token.</span></span>|  
|`mdtMethodSpec`|<span data-ttu-id="62952-129">Token `mdMethodSpec`.</span><span class="sxs-lookup"><span data-stu-id="62952-129">An `mdMethodSpec` token.</span></span>|  
|`mdtGenericParamConstraint`|<span data-ttu-id="62952-130">Token `mdGenericParamConstraint`.</span><span class="sxs-lookup"><span data-stu-id="62952-130">An `mdGenericParamConstraint` token.</span></span>|  
|`mdtString`|<span data-ttu-id="62952-131">Token `mdString`.</span><span class="sxs-lookup"><span data-stu-id="62952-131">An `mdString` token.</span></span>|  
|`mdtName`|<span data-ttu-id="62952-132">Token `mdName`.</span><span class="sxs-lookup"><span data-stu-id="62952-132">An `mdName` token.</span></span>|  
|`mdtBaseType`|<span data-ttu-id="62952-133">Non usato.</span><span class="sxs-lookup"><span data-stu-id="62952-133">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62952-134">Note</span><span class="sxs-lookup"><span data-stu-id="62952-134">Remarks</span></span>  
 <span data-ttu-id="62952-135">Ogni valore è uguale al valore del primo byte nel token di metadati corrispondente.</span><span class="sxs-lookup"><span data-stu-id="62952-135">Each value is equal to the value of the top byte in the corresponding metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62952-136">Requisiti</span><span class="sxs-lookup"><span data-stu-id="62952-136">Requirements</span></span>  
 <span data-ttu-id="62952-137">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62952-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62952-138">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="62952-138">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="62952-139">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62952-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62952-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62952-140">See also</span></span>

- [<span data-ttu-id="62952-141">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="62952-141">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

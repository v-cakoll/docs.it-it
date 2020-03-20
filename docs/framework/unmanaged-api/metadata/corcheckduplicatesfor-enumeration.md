---
title: Enumerazione CorCheckDuplicatesFor
ms.date: 03/30/2017
api_name:
- CorCheckDuplicatesFor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCheckDuplicatesFor
helpviewer_keywords:
- CorCheckDuplicatesFor enumeration [.NET Framework metadata]
ms.assetid: d8ec8d3c-70f7-4cc6-9957-68068fd8f49c
topic_type:
- apiref
ms.openlocfilehash: 04dc12ab4d7d178ebf1575a3260f9f4981972782
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176188"
---
# <a name="corcheckduplicatesfor-enumeration"></a><span data-ttu-id="b53e0-102">Enumerazione CorCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="b53e0-102">CorCheckDuplicatesFor Enumeration</span></span>
<span data-ttu-id="b53e0-103">Specifica i token di metadati che verranno controllati per i duplicati.</span><span class="sxs-lookup"><span data-stu-id="b53e0-103">Specifies the metadata tokens that will be checked for duplicates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b53e0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b53e0-104">Syntax</span></span>  
  
```cpp  
typedef enum CorCheckDuplicatesFor {  
  
    MDDupAll                    = 0xffffffff,  
    MDDupENC                    = MDDupAll,  
    MDNoDupChecks               = 0x00000000,  
    MDDupTypeDef                = 0x00000001,  
    MDDupInterfaceImpl          = 0x00000002,  
    MDDupMethodDef              = 0x00000004,  
    MDDupTypeRef                = 0x00000008,  
    MDDupMemberRef              = 0x00000010,  
    MDDupCustomAttribute        = 0x00000020,  
    MDDupParamDef               = 0x00000040,  
    MDDupPermission             = 0x00000080,  
    MDDupProperty               = 0x00000100,  
    MDDupEvent                  = 0x00000200,  
    MDDupFieldDef               = 0x00000400,  
    MDDupSignature              = 0x00000800,  
    MDDupModuleRef              = 0x00001000,  
    MDDupTypeSpec               = 0x00002000,  
    MDDupImplMap                = 0x00004000,  
    MDDupAssemblyRef            = 0x00008000,  
    MDDupFile                   = 0x00010000,  
    MDDupExportedType           = 0x00020000,  
    MDDupManifestResource       = 0x00040000,  
    MDDupGenericParam           = 0x00080000,  
    MDDupMethodSpec             = 0x00100000,  
    MDDupGenericParamConstraint = 0x00200000,  
  
    MDDupAssembly               = 0x10000000,  
  
    MDDupDefault =
        MDNoDupChecks | MDDupTypeRef | MDDupMemberRef |
        MDDupSignature | MDDupTypeSpec | MDDupMethodSpec  
  
} CorCheckDuplicatesFor;  
```  
  
## <a name="members"></a><span data-ttu-id="b53e0-105">Members</span><span class="sxs-lookup"><span data-stu-id="b53e0-105">Members</span></span>  
  
|<span data-ttu-id="b53e0-106">Membro</span><span class="sxs-lookup"><span data-stu-id="b53e0-106">Member</span></span>|<span data-ttu-id="b53e0-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b53e0-107">Description</span></span>|  
|------------|-----------------|  
|`MDDupAll`|<span data-ttu-id="b53e0-108">Controllare la presenza di duplicati di tutti i token di metadati.</span><span class="sxs-lookup"><span data-stu-id="b53e0-108">Check all metadata tokens for duplicates.</span></span>|  
|`MDDupENC`|<span data-ttu-id="b53e0-109">Non usato.</span><span class="sxs-lookup"><span data-stu-id="b53e0-109">Not used.</span></span>|  
|`MDNoDupChecks`|<span data-ttu-id="b53e0-110">Non controllare i token di metadati per i duplicati.</span><span class="sxs-lookup"><span data-stu-id="b53e0-110">Do not check metadata tokens for duplicates.</span></span>|  
|`MDDupTypeDef`|<span data-ttu-id="b53e0-111">Verificare la `mdTypeDef` presenza di duplicati di token.</span><span class="sxs-lookup"><span data-stu-id="b53e0-111">Check for duplicates of `mdTypeDef` tokens.</span></span>|  
|`MDDupInterfaceImpl`|<span data-ttu-id="b53e0-112">Verificare la `mdInterfaceImpl` presenza di duplicati di token.</span><span class="sxs-lookup"><span data-stu-id="b53e0-112">Check for duplicates of `mdInterfaceImpl` tokens.</span></span>|  
|`MDDupMethodDef`|<span data-ttu-id="b53e0-113">Verificare la `mdMethodDef` presenza di duplicati di token.</span><span class="sxs-lookup"><span data-stu-id="b53e0-113">Check for duplicates of `mdMethodDef` tokens.</span></span>|  
|`MDDupTypeRef`|<span data-ttu-id="b53e0-114">Verificare la `mdTypeRef` presenza di duplicati di token.</span><span class="sxs-lookup"><span data-stu-id="b53e0-114">Check for duplicates of `mdTypeRef` tokens.</span></span>|  
|`MDDupMemberRef`|<span data-ttu-id="b53e0-115">Verificare la `mdMemberRef` presenza di duplicati di token.</span><span class="sxs-lookup"><span data-stu-id="b53e0-115">Check for duplicates of `mdMemberRef` tokens.</span></span>|  
|`MDDupCustomAttribute`|<span data-ttu-id="b53e0-116">Verificare la `mdCustomAttribute` presenza di duplicati di token.</span><span class="sxs-lookup"><span data-stu-id="b53e0-116">Check for duplicates of `mdCustomAttribute` tokens.</span></span>|  
|`MDDupParamDef`|<span data-ttu-id="b53e0-117">Verificare la `mdParamDef` presenza di duplicati di token.</span><span class="sxs-lookup"><span data-stu-id="b53e0-117">Check for duplicates of `mdParamDef` tokens.</span></span>|  
|`MDDupPermission`|<span data-ttu-id="b53e0-118">Verificare la `mdPermission` presenza di duplicati di token.</span><span class="sxs-lookup"><span data-stu-id="b53e0-118">Check for duplicates of `mdPermission` tokens.</span></span>|  
|`MDDupProperty`|<span data-ttu-id="b53e0-119">Verificare la `mdProperty` presenza di duplicati di token.</span><span class="sxs-lookup"><span data-stu-id="b53e0-119">Check for duplicates of `mdProperty` tokens.</span></span>|  
|`MDDupEvent`|<span data-ttu-id="b53e0-120">Verificare la `mdEvent` presenza di duplicati di token.</span><span class="sxs-lookup"><span data-stu-id="b53e0-120">Check for duplicates of `mdEvent` tokens.</span></span>|  
|`MDDupFieldDef`|<span data-ttu-id="b53e0-121">Verificare la `mdFieldDef` presenza di duplicati di token.</span><span class="sxs-lookup"><span data-stu-id="b53e0-121">Check for duplicates of `mdFieldDef` tokens.</span></span>|  
|`MDDupSignature`|<span data-ttu-id="b53e0-122">Verificare la `mdSignature` presenza di duplicati di token.</span><span class="sxs-lookup"><span data-stu-id="b53e0-122">Check for duplicates of `mdSignature` tokens.</span></span>|  
|`MDDupModuleRef`|<span data-ttu-id="b53e0-123">Verificare la `mdModuleRef` presenza di duplicati di token.</span><span class="sxs-lookup"><span data-stu-id="b53e0-123">Check for duplicates of `mdModuleRef` tokens.</span></span>|  
|`MDDupTypeSpec`|<span data-ttu-id="b53e0-124">Verificare la `mdTypeSpec` presenza di duplicati di token.</span><span class="sxs-lookup"><span data-stu-id="b53e0-124">Check for duplicates of `mdTypeSpec` tokens.</span></span>|  
|`MDDupImplMap`|<span data-ttu-id="b53e0-125">Verificare la `mdImplMap` presenza di duplicati di token.</span><span class="sxs-lookup"><span data-stu-id="b53e0-125">Check for duplicates of `mdImplMap` tokens.</span></span>|  
|`MDDupAssemblyRef`|<span data-ttu-id="b53e0-126">Verificare la `mdAssemblyRef` presenza di duplicati di token.</span><span class="sxs-lookup"><span data-stu-id="b53e0-126">Check for duplicates of `mdAssemblyRef` tokens.</span></span>|  
|`MDDupFile`|<span data-ttu-id="b53e0-127">Verificare la `mdFile` presenza di duplicati di token.</span><span class="sxs-lookup"><span data-stu-id="b53e0-127">Check for duplicates of `mdFile` tokens.</span></span>|  
|`MDDupExportedType`|<span data-ttu-id="b53e0-128">Verificare la `mdExportedType` presenza di duplicati di token.</span><span class="sxs-lookup"><span data-stu-id="b53e0-128">Check for duplicates of `mdExportedType` tokens.</span></span>|  
|`MDDupManifestResource`|<span data-ttu-id="b53e0-129">Verificare la `mdManifestResource` presenza di duplicati di token.</span><span class="sxs-lookup"><span data-stu-id="b53e0-129">Check for duplicates of `mdManifestResource` tokens.</span></span>|  
|`MDDupGenericParam`|<span data-ttu-id="b53e0-130">Verificare la `mdGenericParam` presenza di duplicati di token.</span><span class="sxs-lookup"><span data-stu-id="b53e0-130">Check for duplicates of `mdGenericParam` tokens.</span></span>|  
|`MDDupMethodSpec`|<span data-ttu-id="b53e0-131">Verificare la `mdMethodSpec` presenza di duplicati di token.</span><span class="sxs-lookup"><span data-stu-id="b53e0-131">Check for duplicates of `mdMethodSpec` tokens.</span></span>|  
|`MDDupGenericParamConstraint`|<span data-ttu-id="b53e0-132">Verificare la `mdGenericParamConstraint` presenza di duplicati di token.</span><span class="sxs-lookup"><span data-stu-id="b53e0-132">Check for duplicates of `mdGenericParamConstraint` tokens.</span></span>|  
|`MDDupAssembly`|<span data-ttu-id="b53e0-133">Verificare la `mdAssembly` presenza di duplicati di token.</span><span class="sxs-lookup"><span data-stu-id="b53e0-133">Check for duplicates of `mdAssembly` tokens.</span></span>|  
|`MDDupDefault`|<span data-ttu-id="b53e0-134">Verificare la `mdMemberRef`presenza `mdTypeRef` `mdSignature`di `mdTypeSpec`duplicati `mdMethodSpec` di , , , e i token.</span><span class="sxs-lookup"><span data-stu-id="b53e0-134">Check for duplicates of `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, and `mdMethodSpec` tokens.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b53e0-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b53e0-135">Requirements</span></span>  
 <span data-ttu-id="b53e0-136">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b53e0-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b53e0-137">**Intestazione:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="b53e0-137">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="b53e0-138">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b53e0-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b53e0-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b53e0-139">See also</span></span>

- [<span data-ttu-id="b53e0-140">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="b53e0-140">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

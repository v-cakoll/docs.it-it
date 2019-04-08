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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d04f5589ecffbcde59a6ffbe4f3d6c5f0b1040cd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074872"
---
# <a name="corcheckduplicatesfor-enumeration"></a><span data-ttu-id="35b08-102">Enumerazione CorCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="35b08-102">CorCheckDuplicatesFor Enumeration</span></span>
<span data-ttu-id="35b08-103">Specifica il token di metadati che verrà verificato la presenza di duplicati.</span><span class="sxs-lookup"><span data-stu-id="35b08-103">Specifies the metadata tokens that will be checked for duplicates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35b08-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="35b08-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="35b08-105">Membri</span><span class="sxs-lookup"><span data-stu-id="35b08-105">Members</span></span>  
  
|<span data-ttu-id="35b08-106">Member</span><span class="sxs-lookup"><span data-stu-id="35b08-106">Member</span></span>|<span data-ttu-id="35b08-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="35b08-107">Description</span></span>|  
|------------|-----------------|  
|`MDDupAll`|<span data-ttu-id="35b08-108">Controllare tutti i token di metadati per i duplicati.</span><span class="sxs-lookup"><span data-stu-id="35b08-108">Check all metadata tokens for duplicates.</span></span>|  
|`MDDupENC`|<span data-ttu-id="35b08-109">Non usato.</span><span class="sxs-lookup"><span data-stu-id="35b08-109">Not used.</span></span>|  
|`MDNoDupChecks`|<span data-ttu-id="35b08-110">Non archiviare i token di metadati per i duplicati.</span><span class="sxs-lookup"><span data-stu-id="35b08-110">Do not check metadata tokens for duplicates.</span></span>|  
|`MDDupTypeDef`|<span data-ttu-id="35b08-111">Verificare la presenza di duplicati di `mdTypeDef` i token.</span><span class="sxs-lookup"><span data-stu-id="35b08-111">Check for duplicates of `mdTypeDef` tokens.</span></span>|  
|`MDDupInterfaceImpl`|<span data-ttu-id="35b08-112">Verificare la presenza di duplicati di `mdInterfaceImpl` i token.</span><span class="sxs-lookup"><span data-stu-id="35b08-112">Check for duplicates of `mdInterfaceImpl` tokens.</span></span>|  
|`MDDupMethodDef`|<span data-ttu-id="35b08-113">Verificare la presenza di duplicati di `mdMethodDef` i token.</span><span class="sxs-lookup"><span data-stu-id="35b08-113">Check for duplicates of `mdMethodDef` tokens.</span></span>|  
|`MDDupTypeRef`|<span data-ttu-id="35b08-114">Verificare la presenza di duplicati di `mdTypeRef` i token.</span><span class="sxs-lookup"><span data-stu-id="35b08-114">Check for duplicates of `mdTypeRef` tokens.</span></span>|  
|`MDDupMemberRef`|<span data-ttu-id="35b08-115">Verificare la presenza di duplicati di `mdMemberRef` i token.</span><span class="sxs-lookup"><span data-stu-id="35b08-115">Check for duplicates of `mdMemberRef` tokens.</span></span>|  
|`MDDupCustomAttribute`|<span data-ttu-id="35b08-116">Verificare la presenza di duplicati di `mdCustomAttribute` i token.</span><span class="sxs-lookup"><span data-stu-id="35b08-116">Check for duplicates of `mdCustomAttribute` tokens.</span></span>|  
|`MDDupParamDef`|<span data-ttu-id="35b08-117">Verificare la presenza di duplicati di `mdParamDef` i token.</span><span class="sxs-lookup"><span data-stu-id="35b08-117">Check for duplicates of `mdParamDef` tokens.</span></span>|  
|`MDDupPermission`|<span data-ttu-id="35b08-118">Verificare la presenza di duplicati di `mdPermission` i token.</span><span class="sxs-lookup"><span data-stu-id="35b08-118">Check for duplicates of `mdPermission` tokens.</span></span>|  
|`MDDupProperty`|<span data-ttu-id="35b08-119">Verificare la presenza di duplicati di `mdProperty` i token.</span><span class="sxs-lookup"><span data-stu-id="35b08-119">Check for duplicates of `mdProperty` tokens.</span></span>|  
|`MDDupEvent`|<span data-ttu-id="35b08-120">Verificare la presenza di duplicati di `mdEvent` i token.</span><span class="sxs-lookup"><span data-stu-id="35b08-120">Check for duplicates of `mdEvent` tokens.</span></span>|  
|`MDDupFieldDef`|<span data-ttu-id="35b08-121">Verificare la presenza di duplicati di `mdFieldDef` i token.</span><span class="sxs-lookup"><span data-stu-id="35b08-121">Check for duplicates of `mdFieldDef` tokens.</span></span>|  
|`MDDupSignature`|<span data-ttu-id="35b08-122">Verificare la presenza di duplicati di `mdSignature` i token.</span><span class="sxs-lookup"><span data-stu-id="35b08-122">Check for duplicates of `mdSignature` tokens.</span></span>|  
|`MDDupModuleRef`|<span data-ttu-id="35b08-123">Verificare la presenza di duplicati di `mdModuleRef` i token.</span><span class="sxs-lookup"><span data-stu-id="35b08-123">Check for duplicates of `mdModuleRef` tokens.</span></span>|  
|`MDDupTypeSpec`|<span data-ttu-id="35b08-124">Verificare la presenza di duplicati di `mdTypeSpec` i token.</span><span class="sxs-lookup"><span data-stu-id="35b08-124">Check for duplicates of `mdTypeSpec` tokens.</span></span>|  
|`MDDupImplMap`|<span data-ttu-id="35b08-125">Verificare la presenza di duplicati di `mdImplMap` i token.</span><span class="sxs-lookup"><span data-stu-id="35b08-125">Check for duplicates of `mdImplMap` tokens.</span></span>|  
|`MDDupAssemblyRef`|<span data-ttu-id="35b08-126">Verificare la presenza di duplicati di `mdAssemblyRef` i token.</span><span class="sxs-lookup"><span data-stu-id="35b08-126">Check for duplicates of `mdAssemblyRef` tokens.</span></span>|  
|`MDDupFile`|<span data-ttu-id="35b08-127">Verificare la presenza di duplicati di `mdFile` i token.</span><span class="sxs-lookup"><span data-stu-id="35b08-127">Check for duplicates of `mdFile` tokens.</span></span>|  
|`MDDupExportedType`|<span data-ttu-id="35b08-128">Verificare la presenza di duplicati di `mdExportedType` i token.</span><span class="sxs-lookup"><span data-stu-id="35b08-128">Check for duplicates of `mdExportedType` tokens.</span></span>|  
|`MDDupManifestResource`|<span data-ttu-id="35b08-129">Verificare la presenza di duplicati di `mdManifestResource` i token.</span><span class="sxs-lookup"><span data-stu-id="35b08-129">Check for duplicates of `mdManifestResource` tokens.</span></span>|  
|`MDDupGenericParam`|<span data-ttu-id="35b08-130">Verificare la presenza di duplicati di `mdGenericParam` i token.</span><span class="sxs-lookup"><span data-stu-id="35b08-130">Check for duplicates of `mdGenericParam` tokens.</span></span>|  
|`MDDupMethodSpec`|<span data-ttu-id="35b08-131">Verificare la presenza di duplicati di `mdMethodSpec` i token.</span><span class="sxs-lookup"><span data-stu-id="35b08-131">Check for duplicates of `mdMethodSpec` tokens.</span></span>|  
|`MDDupGenericParamConstraint`|<span data-ttu-id="35b08-132">Verificare la presenza di duplicati di `mdGenericParamConstraint` i token.</span><span class="sxs-lookup"><span data-stu-id="35b08-132">Check for duplicates of `mdGenericParamConstraint` tokens.</span></span>|  
|`MDDupAssembly`|<span data-ttu-id="35b08-133">Verificare la presenza di duplicati di `mdAssembly` i token.</span><span class="sxs-lookup"><span data-stu-id="35b08-133">Check for duplicates of `mdAssembly` tokens.</span></span>|  
|`MDDupDefault`|<span data-ttu-id="35b08-134">Verificare la presenza di duplicati `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, e `mdMethodSpec` i token.</span><span class="sxs-lookup"><span data-stu-id="35b08-134">Check for duplicates of `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, and `mdMethodSpec` tokens.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="35b08-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="35b08-135">Requirements</span></span>  
 <span data-ttu-id="35b08-136">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35b08-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35b08-137">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="35b08-137">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="35b08-138">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="35b08-138">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="35b08-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35b08-139">See also</span></span>

- [<span data-ttu-id="35b08-140">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="35b08-140">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
